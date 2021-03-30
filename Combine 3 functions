
import random, pygame

    
################ technical functions ##################

def reset_activation(activation):
    counter = 0
    while counter < len(activation):
        activation[counter]= False
        counter+=1
    
def find_inventory_box(x, y, max_row, max_column):
    counter_y=25
    row=0
    # if it's not change the section is the last section which is the inventory (0)
    section = max_row * max_column
    # loop until you find what box you clicked
    while row < max_row:
        counter_x=15
        column = 0
        
        while column < max_column:
            if x >= counter_x and x <= counter_x + 100 and y >= counter_y and y <= counter_y + 100:
                # activate the new section
                section = (column + (row *max_column))
            counter_x+=130
            column+=1
        counter_y+=145
        row+=1
    return section

def change_sections(section_to_activate, activation):
    inventory_sections=[4, 5, 6, 7, 1, 0, 0]
    reset_activation(activation)
    activation[inventory_sections[section_to_activate]] = True

def get_current_section(x, y, activation):
    counter=0
    while counter < len(activation):
        if activation[counter] == True:
            current_section = counter
            break
        counter+=1
    if current_section == 1:
        if x > 1040:
            current_section = 3
        elif x > 520:
            current_section = 2
        else:
            current_section = 1
    return current_section

def get_current_row(x, y, list_of_rows):
    counter_row=0
    current_row=""
    while counter_row < len(list_of_rows):
        if y >= 25 +counter_row *145 and y <= 125 +counter_row *145:
            current_row=counter_row
        counter_row+=1
    return current_row

def get_current_column(x, y, list_of_a_row, section):
    counter_column=0
    current_column=""
    if section == 1 or section == 2:
        x-=520 *section
    while counter_column < len(list_of_a_row):
        if x >= 15 +counter_column *130 and x <= 115 +counter_column *130:
            current_column=counter_column
        counter_column+=1
    return current_column

def get_current_box(x, y, section_amounts, activation):
    section_row_column=[]
    section_row_column.append(get_current_section(x, y, activation) -1)
    # you can't combine in your inventory
    if section_row_column[0] != -1:
        section_row_column.append(get_current_row(x, y, section_amounts[section_row_column[0]]))
        # is it in a box?
        if section_row_column[1] != "":
            section_row_column.append(get_current_column(x, y, section_amounts[section_row_column[0]][section_row_column[1]], section_row_column[0]))
            # is it in a box?
            if section_row_column[2] != "":
                return section_row_column       
    return False
    
def get_section_index(box, array):
    counter = 0
    while counter < len(array):
        if box == array[counter]:
            return counter
        counter+=1

def get_index(List, Object):
    counter = 0
    while counter < len(List):
        if Object == List[counter]:
            return counter
        counter+=1
    if counter == len(List):
        return False

    
    
# what to worry about when adding a new section:
# have all the draw functions
# add a new thing called section#_amounts and section#_row1 ...
# add the if section# is activated change window size
# 



#######################       COMBINING       ###########################



# what to worry about when adding something combineable:
#
#
#

def get_number_of_requirements(section, row, column, required_items):
    # get the length of the tuple in required items
    number_of_requirements=len(required_items[section][row][column])
    return number_of_requirements

def check_requirements(section, row, column, number_of_requirements, s_amounts, num_amounts, section_amounts, turn, combinations, items_crafted, time_objects, time_starting_turns):
    y_n = False
    # check if the item increases over time
    if s_amounts[section][row][column][len(s_amounts[section][row][column])-1] in time_objects:
        counter = get_section_index((section, row, column), time_objects)
        if time_starting_turns[counter][0] == True:
            return False
    counter = 0
    if s_amounts[section][row][column][0] == "crafting table" or s_amounts[section][row][column][0] == "craft":
        # increase the counter so that you ignore the "crafting table" and "craft"
        counter+=1
        if s_amounts[section][row][column][0] == "crafting table":
            # if you don't have a crafting table it's atomatically false
            if section_amounts[0][2][2] < 1:
                y_n = False
                return y_n
            
    # number_of_requirments -1 because number_of_requirments is the output and we're checking the output
    while counter < number_of_requirements-1:
        required_item_tuple = s_amounts[section][row][column][counter]
        # e.g. (0,1,1) is coarse dirt 0 ist the section 1 is the row and 1 is the column
        required_amount = num_amounts[section][row][column][counter]
                                              
        place = 0
        # if the first part of the tuple is "mineable"
        # you need the mined version
        if required_item_tuple[place] == "mineable":
            place +=1
            # check if you have the mined version 
            if section_amounts[required_item_tuple[place]][required_item_tuple[place +1]][required_item_tuple[place +2]][1] >= num_amounts[section][row][column][counter]:
                y_n = True
            else:
                y_n = False
                return y_n
        # check if you have the current required item and at least the minimum amount
        elif section_amounts[required_item_tuple[place]][required_item_tuple[place +1]][required_item_tuple[place +2]] >= num_amounts[section][row][column][counter]:
            # continue the loop until you either don't have a resource or you have everything
            y_n = True
        else:
            y_n = False
            return y_n
        counter+=1
    turn[0] += 3
    combinations[0] += 1
    if s_amounts[section][row][column][0] == "crafting table" or s_amounts[section][row][column][0] == "craft":
        turn[0] += 2
        combinations[0] -= 1
        items_crafted[0] += 1
    return y_n

def ask_y_n_for_tool(section, row, column, number_of_requirements, s_amounts, section_amounts, turn):
    
    y_n_input = "yes"
    output_item_tuple = s_amounts[section][row][column][number_of_requirements -1]
    place = 0
    # check if the output is mineable
    if type(s_amounts[section][row][column][number_of_requirements -1]) == tuple and type(s_amounts[section][row][column][number_of_requirements -1][0]) == str:
        return True
    # check if it's a tool
    if type(section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]]) == list and section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]][0] == "tool":
        # if the tool already has maximum durability
        if section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]][1] == section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]][2]:
            print("You already have this tool")
            y_n_input="no"
        # if the tool's been partly used
        elif section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]][1] >= 1:
            y_n_input=input("You already have this tool, but would you like to make a new one that overwrites the old one? ")
        # if you don't have a tool
        else:
            y_n_input=input("Are you sure you want to craft this tool? ")
    
    y_n = True
    # check if the player didn't say yes
    if y_n_input.lower() != "yes":
        y_n = False
        turn[0]-=5
    return y_n

def change_tool_durability(section, row, column, number_of_requirements, s_amounts, section_amounts, y_n):
    
    output_item_tuple = s_amounts[section][row][column][number_of_requirements -1]
    # check if the output is mineable
    if type(s_amounts[section][row][column][number_of_requirements -1]) == tuple and type(s_amounts[section][row][column][number_of_requirements -1][0]) == str:
        return
    # check if it's a tool
    if type(section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]]) == list and section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]][0] == "tool" and y_n == True:
        # set the tool to maximum durability 
        # the list is ["tool", current_durability, maximum durability]
        section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]][1] = section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]][2]

def decrease_requirements(section, row, column, number_of_requirements, s_amounts, num_amounts, section_amounts):
    
    counter=0
    # to avoid "crafting", etc
    if type(s_amounts[section][row][column][0]) == str:
        counter+=1
    # number_of_requirments -1 because number_of_requirments is the output and we're decresing the input
    while counter < number_of_requirements-1:
        # mineable should not be counted
        if s_amounts[section][row][column][counter][0] == "mineable":
            section_amounts[s_amounts[section][row][column][counter][1]][s_amounts[section][row][column][counter][2]][s_amounts[section][row][column][counter][3]][1]-=num_amounts[section][row][column][counter]
            # decrease the mined version
        else:
            # decrease the amount from the required item
            section_amounts[s_amounts[section][row][column][counter][0]][s_amounts[section][row][column][counter][1]][s_amounts[section][row][column][counter][2]]-=num_amounts[section][row][column][counter]
        counter+=1

def increase_output(section, row, column, number_of_requirements, s_amounts, num_amounts, section_amounts):
    
    output_amount = num_amounts[section][row][column][number_of_requirements -1]
    output_item_tuple = s_amounts[section][row][column][number_of_requirements -1]
    # check if what you are going to get needs to be mined later
    if output_item_tuple[0] == "mineable":
        # give the user the unmined version
        section_amounts[output_item_tuple[1]][output_item_tuple[2]][output_item_tuple[3]][2] +=output_amount
    # if it's a tool don't do anything
    elif type(section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]]) == list and section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]][0] == "tool":
        return
    else:
        # increase the last item in the s_amounts list (which is what you want to increase) by the num_amount
        section_amounts[output_item_tuple[0]][output_item_tuple[1]][output_item_tuple[2]] +=output_amount

def COMBINE(section, row, column, section_amounts, turn, combinations, items_crafted, time_objects, time_starting_turns):
    
    ###############   what resources you combine   #############
    
    # guide:
    # "not combineable" means you can not combine stuff to aquire this item
    # the last tuple is what you get
    # the other tuples are what you need
    # "crafting table" means you need a crafting table
    # if the tuple has "mineable" in it, it will make sure that the resource is mined or given in the not mined form 
    # row 2
    # the tuple is the amount of each item you need 
    # for example a stick needs 2 wood planks and you get 4 sticks ("craft",2,4)
    
    # section 1 resources requirements
    s1_row_1=["not combinable", "not combinable", ((0,0,0),(0,0,1),(0,0,2)), "not combinable"]
    num1_row_1=["not combinable", "not combinable", ( 1   ,   1   ,   1   ), "not combinable"]

    s1_row_2=[((0,0,1),(0,0,3),(0,1,0)), ((0,0,2),(0,1,0),(0,1,1)), ((0,0,3),(0,1,1),(0,1,2)), "not combinable"]
    num1_row_2=[( 1   ,   1   ,   1   ), (   1   ,   1   ,   1   ), (   1   ,   1   ,   2   ), "not combinable"]
    
    s1_row_3=["not combinable", ((0,2,0),(0,1,3),(0,2,1)), ("craft",(0,2,1),(0,2,2)), ("craft",(0,2,1),(0,2,3))]
    num1_row_3=["not combinable", ( 1   ,   1   ,   1   ), ("craft",   4   ,   1  ),  ("craft",   2   ,   4   )]
    
    s1_amounts=[s1_row_1, s1_row_2, s1_row_3]
    num1_amounts=[num1_row_1, num1_row_2, num1_row_3]

    
    # section 2 resources requirements
    s2_row_1=[((0,1,2),(0,1,3),(1,0,0)), ((1,0,0),(0,1,2),("mineable", 1,0,1)), ("crafting table",("mineable", 1,0,1),(1,0,2)), (("mineable", 1,0,1),(0,1,2),(1,0,3))]
    num2_row_1=[( 1   ,   1   ,   1   ), (   1   ,   1   ,               2)   , ("crafting table",          8        ,   1)   , (          1        ,   1   ,   2   )]
    
    s2_row_2=["not combinable", ("crafting table",(1,1,0),(1,1,1)), ((1,0,0),(0,1,3),("mineable", 1,1,2)), ((2,1,1),(1,1,3))]
    num2_row_2=["not combinable", ("crafting table", 3   ,   3   ), (   1   ,   1,             2        ), (   5   ,   1   )]
    
    s2_row_3=[("crafting table",(1,1,3),(1,2,0)), ("crafting table",(1,1,3),(1,2,1)), ((1,2,1),(1,2,0),(1,2,2)), ((1,2,2),(1,2,1),(1,2,3))]
    num2_row_3=[("crafting table", 5   ,   1   ), ("crafting table",   3   ,   1   ), (   1   ,   1   ,   1   ), (   2   ,  -2   ,   1   )]
    
    s2_amounts=[s2_row_1, s2_row_2, s2_row_3]
    num2_amounts=[num2_row_1, num2_row_2, num2_row_3]
    
    
    # section 3 resources requirements
    s3_row_1=[((0,0,0),(2,0,0)), ((2,0,0),(1,1,1),(2,0,1)), "not combinable", ((1,2,2),(2,0,2),(1,2,1),(2,0,3))]
    num3_row_1=[( 30  ,   2   ), (   1   ,   1   ,   1   ), "not combinable", (   1   ,   1   ,  -1   ,   1   )]
    
    s3_row_2=[((1,1,3),(0,2,3),(2,1,0)), ("craft",(2,1,0),(2,1,1)), ("craft",(2,0,3),(2,1,1),(2,1,2)), ((0,0,0),(0,2,3),(2,1,3))]
    num3_row_2=[( 1   ,   1   ,   1   ), ("craft",   1   ,   3   ), ("craft",   1   ,   1   ,   2   ), (   1   ,   1   ,   2   )]
    
    s3_row_3=["not combinable", ((2,1,2),(2,2,0),(2,2,1)), "diamond", ((2,2,2),(2,2,1),(2,2,3))]
    num3_row_3=["not combinable", ( 1   ,   1   ,   1   ), "diamond", (   1   ,   1   ,   1   )]
    
    s3_amounts=[s3_row_1, s3_row_2, s3_row_3]
    num3_amounts=[num3_row_1, num3_row_2, num3_row_3]
    
    
    # section 4 resources requirements
    s4_row_1=["not combinable", ("craft",(0,2,1),(3,0,1)), "not combinable", "not combinable", "not combinable"]
    num4_row_1=["not combinable", ("craft", 2   ,   4   ), "not combinable", "not combinable", "not combinable"]
    
    s4_row_2=[("crafting table", (0,2,1),(0,2,3),(3,1,0)), ("crafting table", ("mineable", 1,0,1), (0,2,3),(3,1,1)), ("crafting table", (1,1,3), (0,2,3),(3,1,2)), ("crafting table", (2,2,1), (0,2,3),(3,1,3)), ("crafting table", (0,2,1),(0,2,3),(3,1,4))]
    num4_row_2=[("crafting table",  3   ,   2   ,   1   ), ("crafting table",           3        ,    2   ,   1   ), ("crafting table",    3   ,    2   ,   1   ), ("crafting table",    3   ,    2   ,   1   ), ("crafting table",    2   ,   1   ,   1   )]
    
    s4_row_3=[("crafting table", ("mineable", 1,0,1), (0,2,3),(3,2,0)), ("crafting table", (1,1,3),(0,2,3),(3,2,1)), ("crafting table", (2,2,1),(0,2,3),(3,2,2)), ("crafting table", "string", (0,2,3),(3,2,3)), ("crafting table", (0,1,3),(0,2,3), "feather",(3,2,4))]
    num4_row_3=[("crafting table",        2         ,    1   ,   1   ), ("crafting table",    2   ,   1   ,   1   ), ("crafting table",    2   ,   1   ,   1   ), ("crafting table",     3   ,    3   ,   1   ), ("crafting table",    1   ,   1   ,     1    ,   4   )]
    
    s4_amounts=[s4_row_1, s4_row_2, s4_row_3]
    num4_amounts=[num4_row_1, num4_row_2, num4_row_3]
    
    
    # section 5 resources requirements
    s5_row_1=["not combinable", ((0,2,1),(0,2,3)), "not combineable", "not combineable", "not combineable", ((1,1,3),(0,2,3),(2,1,0)), ("craft",(2,1,0),(2,1,1))]
    num5_row_1=["not combinable", ( 2   ,   4   ), "not combineable", "not combineable", "not combineable", ( 1   ,   1   ,   1   ), ("craft",   1   ,   3   )]
    
    s5_row_2=[("crafting table", ("mineable", 1,0,1),(0,2,3),(4,1,0)), ("crafting table", (1,1,3),(0,2,3),(4,1,1)), ("crafting table", (2,2,1),(0,2,3),(4,1,2)), "not combineable", "not combineable", "not combineable", ((4,1,4), (1,2,3), (4,1,6))]
    num5_row_2=[("crafting table",        2         ,   2   ,   1   ), ("crafting table",  2   ,   2   ,   1   ), ("crafting table",    2   ,   2   ,   1   ), "not combineable", "not combineable", "not combineable",   (   25  ,    1   ,    1   )]
    
    s5_row_3=["not combineable", ( (0,0,0), (4,1,6), (4,2,1)), "not combineable", "not combineable", ((4,2,3), (4,1,6), (4,2,4)), ((0,0,0), (0,2,3), (4,2,5)), ((4,2,5), (2,1,1), (4,2,6))]
    num5_row_3=["not combineable", (  25  ,    1   ,    1   ), "not combineable", "not combineable", (   25   ,    1   ,    1   ), (   3   ,    3   ,    1   ), (   1   ,    10  ,    1   )]
    
    s5_amounts=[s5_row_1, s5_row_2, s5_row_3]
    num5_amounts=[num5_row_1, num5_row_2, num5_row_3]
    
    
    # all section amounts so that they can be referenced to
    s_amounts=[s1_amounts, s2_amounts, s3_amounts, s4_amounts, s5_amounts]
    num_amounts=[num1_amounts, num2_amounts, num3_amounts, num4_amounts, num5_amounts]
    
    
    
    ################################################################
    
    number_of_requirements = get_number_of_requirements(section, row, column, s_amounts)
    # check if it's "not combineable"
    if type(s_amounts[section][row][column]) == str:
        return
    # get a boolean saying if you have all the requirements
    have_all_requirements = check_requirements(section, row, column, number_of_requirements, s_amounts, num_amounts, section_amounts, turn, combinations, items_crafted, time_objects, time_starting_turns)
    
    if have_all_requirements == True:
        y_n_for_tool = ask_y_n_for_tool(section, row, column, number_of_requirements, s_amounts, section_amounts, turn)
        if y_n_for_tool == True:
            change_tool_durability(section, row, column, number_of_requirements, s_amounts, section_amounts, y_n_for_tool)
            decrease_requirements(section, row, column, number_of_requirements, s_amounts, num_amounts, section_amounts)
            increase_output(section, row, column, number_of_requirements, s_amounts, num_amounts, section_amounts)

#########################   mining   #############################



# what to worry about when adding something mineable:
#
#
#

def check_correct_tool(mineable_objects, index, all_tools_boxes, current_tool, section_amounts):
    have_tool = False
    if mineable_objects[index][0] == "needs tool":
        if current_tool == 0:
            return have_tool
        if current_tool in range(mineable_objects[index][1][0], mineable_objects[index][1][1]):
            # if you have more than 1 durability on the tool you are using
            if current_tool != 0 and section_amounts[all_tools_boxes[current_tool][0]][all_tools_boxes[current_tool][1]][all_tools_boxes[current_tool][2]][1] >= 1:
                have_tool = True
            else:
                print("You don't have this tool")
        else:
            print("You don't have the right tool equipped")
    # if you don't need a tool you can skip it
    else:
        have_tool = True
    return have_tool

def have_breakable_object(section, row, column, section_amounts):
    no_requirements = [[0,0,0], [0,0,1], [0,2,0]]
    have_object = False
    if type(section_amounts[section][row][column]) == list and section_amounts[section][row][column][0] == "mineable":
        if section_amounts[section][row][column][2] >= 1:
            have_object = True
    # if it's blank
    elif [section, row, column] in no_requirements:
        have_object = True
    elif type(section_amounts[section][row][column]) == list and section_amounts[section][row][column][0] == "reference":
        if section_amounts[section_amounts[section][row][column][1]][section_amounts[section][row][column][2]][section_amounts[section][row][column][3]] >= 1:
            have_object = True
    else:
        if section_amounts[section][row][column] >= 1:
            have_object = True
    return have_object

def decrease_breakable_object(section, row, column, section_amounts):
    dont_decrease  = [[0,0,0], [0,0,1], [0,2,0]]
    if type(section_amounts[section][row][column]) == list and section_amounts[section][row][column][0] == "mineable":
        section_amounts[section][row][column][2]-=1
    elif [section, row, column] in dont_decrease:
        return
    elif type(section_amounts[section][row][column]) == list and section_amounts[section][row][column][0] == "reference":
        section_amounts[section_amounts[section][row][column][1]][section_amounts[section][row][column][2]][section_amounts[section][row][column][3]]-=1
    else:
        section_amounts[section][row][column]-=1
        
def decrease_tool_durability(section_amounts, mineable_objects, index, section, row, column, current_tool, all_tools_boxes):
    if mineable_objects[index][0] == "needs tool":
        section_amounts[all_tools_boxes[current_tool][0]][all_tools_boxes[current_tool][1]][all_tools_boxes[current_tool][2]][1] -= 1
    
def increase_mined_object(section, row, column, section_amounts, mineable_objects, mined_output, index, random_objects, random_object_increase, turn, blocks_broken):
    if type(section_amounts[section][row][column]) == list and section_amounts[section][row][column][0] == "mineable":
        section_amounts[section][row][column][1]+=1
    # if it's randomized
    elif [section, row, column] in random_objects:
        # get the random_object index
        index = get_section_index([section, row, column], random_objects)
        # gets a random number from 1 to #
        random_number = random.randint(random_object_increase[index][1], random_object_increase[index][2])
        if random_number == 1:
            section_amounts[random_object_increase[index][0][0]][random_object_increase[index][0][1]][random_object_increase[index][0][2]] += random_object_increase[index][3]
    # if it's the mushroom block
    elif [section, row, column] == [0,0,1]:
        random_number = random.randint(1,4)
        if random_number == 1:
            section_amounts[0][0][1] += random.randint(1,3)
        random_number = random.randint(1,4)
        if random_number == 1:
            section_amounts[0][0][0] += 1
        turn[0] +=1
    # if it's a spawn egg
    elif mined_output[index][0] == "spawn egg":
        # one spawn egg is in a list with the object, a list of tuples with the item and their randomized range, and the number of items dropped
        spawn_egg_list = [ [[2,0,1], [([0,2,3],[1,6]), ([2,0,2],[1,3]), ([1,1,1], [1,3]) ], 2] ]
        index = 0
        while index < len(spawn_egg_list):
            if spawn_egg_list[index][0] == [section, row, column]:
                break
            index+=1
        items_increased = 0
        # while it's less than the amount of random items dropped by the mob
        while items_increased < spawn_egg_list[index][2]:
            random_int = random.randint(0, len(spawn_egg_list[index][1])-1)
            section_amounts[spawn_egg_list[index][1][random_int][0][0]][spawn_egg_list[index][1][random_int][0][1]][spawn_egg_list[index][1][random_int][0][2]] += random.randint(spawn_egg_list[index][1][random_int][1][0],spawn_egg_list[index][1][random_int][1][1])
            # remove the item from the list
            spawn_egg_list[index][1].remove(spawn_egg_list[index][1][random_int])
            items_increased+=1
            
    elif mined_output[index][0] == "fillable":
        # make sure you have water to fill the object with
        if section_amounts[1][2][3] >= 1:
            section_amounts[mined_output[index][1][0]][mined_output[index][1][1]][mined_output[index][1][2]] += 1
        # otherwise give the user back their empty object and decrease the turn
        else:
            section_amounts[mineable_objects[index][1][0]][mineable_objects[index][1][1]][mineable_objects[index][1][2]] += 1
            turn[0]-=2
    else:
        section_amounts[mined_output[index][0]][mined_output[index][1]][mined_output[index][2]]+=1
    turn[0] +=2
    blocks_broken[0] += 1

def mining(section, row, column, mineable_objects_boxes, mineable_objects, mined_output, section_amounts, current_tool, all_tools_boxes, turn, blocks_broken):
    random_objects = [[0,0,0], [0,2,0], [2,1,3]]
    # [0,0,0] is the output 1,3 is the range and 1 is the amount
    random_object_increase = [([0,0,0], 1,3, 1), ([0,2,0], 1,10, 1), ([2,2,0], 1,6, 1)]
    index = get_section_index([section, row, column], mineable_objects_boxes)
    have_tool = check_correct_tool(mineable_objects, index, all_tools_boxes, current_tool, section_amounts)
    if have_tool == False:
        return
    have_object = have_breakable_object(section, row, column, section_amounts)
    if have_object == False:
        return
    decrease_breakable_object(section, row, column, section_amounts)
    decrease_tool_durability(section_amounts, mineable_objects, index, section, row, column, current_tool, all_tools_boxes)
    increase_mined_object(section, row, column, section_amounts, mineable_objects, mined_output, index, random_objects, random_object_increase, turn, blocks_broken)
    
        
        


########################   smelting   ##########################



# what to worry about when adding something smeltable:

# add the item to the smeltable objects and smelted output lists



def smelt_requirements(quantity, smeltable_objects, index, section_amounts):
    y_n = False
    Continue = False
    # if it's mineable check the mined version
    if type(section_amounts[smeltable_objects[index][0]][smeltable_objects[index][1]][smeltable_objects[index][2]]) == list:
        if section_amounts[smeltable_objects[index][0]][smeltable_objects[index][1]][smeltable_objects[index][2]][1] >= quantity:
            Continue = True
    elif section_amounts[smeltable_objects[index][0]][smeltable_objects[index][1]][smeltable_objects[index][2]] >= quantity:
        Continue = True
    if Continue == True:
        if section_amounts[1][0][2] >= 1:
            if section_amounts[1][0][0] >= 1:
                section_amounts[1][0][0]-=1
                y_n = True
            else:
                print("You need coal to smelt items. ")
        else:
            print("You need a furnace to smelt items. ")
    return y_n

def reduce_smeltable_object(smeltable_objects, index, quantity, section_amounts):
    # if it's mineable
    if type(section_amounts[smeltable_objects[index][0]][smeltable_objects[index][1]][smeltable_objects[index][2]]) == list:
        section_amounts[smeltable_objects[index][0]][smeltable_objects[index][1]][smeltable_objects[index][2]][1]-=quantity
    else:
        section_amounts[smeltable_objects[index][0]][smeltable_objects[index][1]][smeltable_objects[index][2]]-=quantity
    
def increase_smelted_object(smelted_output, index, quantity, section_amounts, turn):
    # if the output has to be mined
    if type(section_amounts[smelted_output[index][0]][smelted_output[index][1]][smelted_output[index][2]]) == list:
        section_amounts[smelted_output[index][0]][smelted_output[index][1]][smelted_output[index][2]][2]+=quantity
    else:
        section_amounts[smelted_output[index][0]][smelted_output[index][1]][smelted_output[index][2]]+=quantity
    turn[0]+=7*quantity



##################   Time   #####################



def check_for_time_object_combination(section_amounts, turn, time_starting_turns, time_objects, how_often):
    counter = 0
    # loop through all time objects
    while counter < len(time_objects):
        # if the time object amount is over 1
        if section_amounts[time_objects[counter][0]][time_objects[counter][1]][time_objects[counter][2]] >= 1:
            if time_starting_turns[counter][0] == False:
                time_starting_turns[counter][1] = turn[0]
                # the user now has the time object
                time_starting_turns[counter][0] = True
                # decrease the amount by one
                section_amounts[time_objects[counter][0]][time_objects[counter][1]][time_objects[counter][2]] -= 1
                when_it_will_be_done = ["Your Cauldron will fill with water on turn ", "Your farm will grow to the next stage on turn ", "Your farm will grow to the next stage on turn " ]
                extra = ["", "It will be fully grown on turn " +str(time_starting_turns[counter][1] + how_often[2]*3), "It will be fully grown on turn " +str(time_starting_turns[2][1] + how_often[2]*3)]
                print(when_it_will_be_done[counter] +str((time_starting_turns[counter][1] + how_often[counter])))
                if extra[counter] != "":
                    print(extra[counter])
                print("A yellow outline indicates that you will be getting this item over time")
        counter+=1
                
def change_time_object_amounts(section_amounts, turn, time_starting_turns, time_object_limit, time_objects, time_object_section, how_often, activation, window):
    
    counter = 0
    while counter < len(time_starting_turns):
        
        if type(time_starting_turns[counter]) == list:
            if time_starting_turns[counter][0] == True and activation[time_object_section[counter]] == True:
                x = 0
                # so that it is accurate when in the main area
                if time_objects[counter][0] >= 1 and time_objects[counter][0] <= 2:
                    x = time_objects[counter][0] *4
                
                if turn[0] >= time_starting_turns[counter][1] + how_often[counter] and section_amounts[time_objects[counter][0]][time_objects[counter][1]][time_objects[counter][2]] < time_object_limit[counter]:
                    time_starting_turns[counter][1] += how_often[counter]
                    section_amounts[time_objects[counter][0]][time_objects[counter][1]][time_objects[counter][2]] += 1
        counter +=1




# how to add a new section
"""
Step one   drawing it out

Get all the drawing functions for each object
Make sure to use the draw functions like draw_circle() or draw_block()
Then, make sure to change the window size when the section is activated
Make it accessible from the inventory
In the main area, you will need the x and y coordinates, 
the functions to draw the objects, the title offset, and the titles and names
then fill out the draw_setion requirements


Step two   adding the amounts

On the top of the main section make "# of rows" lists
each with "# of columns" slots and a section#_amounts list containing them
Start all items at 0
If the object is mineable make the slot a list and have
["mineable", "mined amount" (starts as 0), unmined amount (also starts at 0)]
For items from other sections ["reference", original section, original row, original column]
For tools ["tool", "current durability" (starts as 0), max durability]

Step three   making it work

Go through instructions for combining
if it's minable or smeltable read those instructions

Now your done!
"""










