"""

Then add working farm
carrot 1-4
wheat 1 and 0-3 seeds
Don't forget 15x Bone meal (10x Tree)
with hoe more common seeds and mushrooms
"""

# started February 12th  (Ski break project)
"""
Combine_3

Description:
"""
import pygame, random, functions, drawing_functions,  pygame.freetype
pygame.init()

# section 1 resources amounts
section_1_row_1=[50,50,0,0]
section_1_row_2=[0,0,20,20]
section_1_row_3=[0,0,1,20]
section_1_amounts=[section_1_row_1, section_1_row_2, section_1_row_3]
# section 2 resources amounts
section_2_row_1=[0,["mineable", 0, 0],0,0]
section_2_row_2=[0,20,["mineable", 0, 0],20]
section_2_row_3=[0,0,0,1]
section_2_amounts=[section_2_row_1, section_2_row_2, section_2_row_3]
# section 3 resources amounts
section_3_row_1=[20,0,0,0]
section_3_row_2=[0,0,0,0]
section_3_row_3=[0,0,0,0]
section_3_amounts=[section_3_row_1, section_3_row_2, section_3_row_3]
# section 4 resources amounts
section_4_row_1=[["reference", 0, 2, 2], ["reference", 0, 2, 3],["refer and mine", 1, 0, 1],["reference", 1, 1, 3], ["reference", 2, 2, 1]]
section_4_row_2=[["tool", 0, 10],["tool", 0, 20], ["tool", 0, 50], ["tool", 0, 150], ["tool", 0, 10]]
section_4_row_3=[["tool", 0, 20],["tool", 0, 50],["tool", 0, 150],["tool", 0, 30], 0]
section_4_amounts=[section_4_row_1, section_4_row_2, section_4_row_3]
# section 5 resources amounts
section_5_row_1=[["reference", 0, 2, 2], ["reference", 0, 2, 3],["refer and mine", 1, 0, 1],["reference", 1, 1, 3],["reference", 2, 2, 1], ["reference", 2, 1, 0], ["reference", 2, 1, 1]]
section_5_row_2=[["tool", 0, 30], ["tool", 0, 75],["tool", 0, 150], ["reference", 0, 0, 3], 0, ["reference", 1, 2, 3], 2]
section_5_row_3=[["reference", 0, 0, 0], 0, 0, 50, 0, 0, 0, ""]
section_5_amounts=[section_5_row_1, section_5_row_2, section_5_row_3]
# all section amounts so that they can be referenced to
section_amounts=[section_1_amounts, section_2_amounts, section_3_amounts, section_4_amounts, section_5_amounts]

# section rows and columns
section_0_rows_columns = [3,2]
section_1_rows_columns = [4,3]
section_2_rows_columns = [4,3]
section_3_rows_columns = [4,3]
section_4_rows_columns = [5,3]
section_5_rows_columns = [7,3]
sections_rows_columns = [section_0_rows_columns, section_1_rows_columns, section_2_rows_columns, section_3_rows_columns, section_4_rows_columns, section_5_rows_columns]

# starting window dimensions
window_dimensions=[0,0]

# current tool
current_tool=0
wood_pickaxe = 1
stone_pickaxe = 2 
iron_pickaxe = 3
diamond_pickaxe = 4
wood_sword = 5
stone_sword = 6
iron_sword = 7
diamond_sword = 8
bow = 9
stone_hoe = 10
iron_hoe = 11
diamond_hoe = 12
all_tools = ["", wood_pickaxe, stone_pickaxe, iron_pickaxe, diamond_pickaxe , wood_sword , stone_sword , iron_sword , diamond_sword , bow , stone_hoe , iron_hoe , diamond_hoe]
all_tools_names = ["", "Wood pickaxe", "Stone pickaxe", "Iron pickaxe", "Diamond pickaxe", "Wood sword", "Stone sword", "Iron sword", "Diamond sword", "Bow", "Stone hoe", "Iron hoe", "Diamond hoe"]
all_tools_boxes = ["", [3,1,0], [3,1,1], [3,1,2], [3,1,3], [3,1,4], [3,2,0], [3,2,1], [3,2,2], [3,2,3], [4,1,0], [4,1,1], [4,1,2]]

# what sections should be drawn
section_2_always_true = False
section_3_always_true = False

smelt_numbers=["", pygame.K_1, pygame.K_2, pygame.K_3, pygame.K_4, pygame.K_5, pygame.K_6, pygame.K_7, pygame.K_8]

# section positions
inventory=0
crafting=1
water=2
diamond=3
tools=4
farming=5

# time

time_starting_turns = [[False, 0], [False, 0], [False, 0]]
time_objects = [(1,2,0), (4,2,1), (4,2,4)]
time_object_section = [water, farming, farming]
how_often = [200, 100, 100]
time_object_limit =[3, 3, 3]

# start the grid in position 1, i.e. crafting
activation=[False, True, False, False, False, False]
change_window_size=True

# player stats
turn = [0]
combinations = [0]
blocks_broken = [0]
items_crafted = [0]
hp = [20]
hunger = [20]
xp = [0]
xp_level = [0]

game=True

while game:
    x = 0
    y = 0
    
    for event in pygame.event.get():
        if event.type == pygame.KEYDOWN:
            
            # if e is pressed go to the inventory
            if event.key == pygame.K_e:
                functions.reset_activation(activation)
                activation[inventory]=True
                change_window_size=True


            # if space is pressed COMBINE!!!
            elif event.key == pygame.K_SPACE:
                x, y = pygame.mouse.get_pos()
                # gets a list with the section, row, and column in that order
                section_row_column = functions.get_current_box(x, y, section_amounts, activation)
                # if you aren't not in a box
                if section_row_column != False:
                    functions.COMBINE(section_row_column[0], section_row_column[1], section_row_column[2], section_amounts, turn, combinations, items_crafted, time_objects, time_starting_turns)                
                
                
            elif event.key == pygame.K_RETURN:
                x, y = pygame.mouse.get_pos()
                # if you're in the inventory
                if activation[inventory] == True:
                    section_to_activate = functions.find_inventory_box(x, y, 2, 3)
                    functions.change_sections(section_to_activate, activation)
                    change_window_size=True
                # mining
                else:
                    x, y = pygame.mouse.get_pos()
                    section_row_column = functions.get_current_box(x, y, section_amounts, activation)
                    # if it's not not in a box
                    if section_row_column != False:
                        mineable_objects_boxes = [[0,0,0], [0,0,1], [0,0,2], [0,1,2], [0,2,0], [1,0,1], [1,1,2], [1,2,1], [2,0,1], [2,1,3], [4,1,3]]
                        if section_row_column in mineable_objects_boxes:
                            mineable_objects = [[0,0,0], [0,0,0], [0,0,2], [0,1,2], [0,0,0], ["needs tool", (0,4), [1,0,1], 2], ["needs tool", (1,4), [1,1,2], 2], ["fillable", [1,2,1]], [2,0,1], [2,1,3], ["needs tool", (9,12), [0,0,3]]]
                            mined_output = [[0,0,0], [0,0,1], [0,0,3], [0,1,3], [0,2,0], ["needs tool", [1,0,1], 1], ["needs tool", [1,1,2], 1], ["fillable", [1,2,2]], ["spawn egg", [2,0,1]], [2,2,0], [4,1,4]]
                            functions.mining(section_row_column[0], section_row_column[1], section_row_column[2], mineable_objects_boxes, mineable_objects, mined_output, section_amounts, current_tool, all_tools_boxes, turn, blocks_broken)
                        # changing your current tool
                        elif type(section_amounts[section_row_column[0]][section_row_column[1]][section_row_column[2]]) == list and section_amounts[section_row_column[0]][section_row_column[1]][section_row_column[2]][0] == "tool":
                            index = functions.get_section_index(section_row_column[0], section_row_column[1], section_row_column[2], all_tools_boxes)
                            current_tool = all_tools[index]
                        
                                    
            # if a number is pressed the user wants to smelt something
            elif event.key in smelt_numbers:
                x, y = pygame.mouse.get_pos()
                section_row_column = functions.get_current_box(x, y, section_amounts, activation)
                smeltable_objects = [[1,0,3], [1,1,2]]
                smelted_output = [[1,1,0], [1,1,3]]
                if section_row_column in smeltable_objects:
                    smelt_quantity = functions.get_index(smelt_numbers, event.key)
                    smeltable_object_index = functions.get_section_index(section_row_column[0], section_row_column[1], section_row_column[2], smeltable_objects)
                    y_n = functions.smelt_requirements(smelt_quantity, smeltable_objects, smeltable_object_index, section_amounts)
                    if y_n == True:
                        functions.reduce_smeltable_object(smeltable_objects, smeltable_object_index, smelt_quantity, section_amounts)
                        functions.increase_smelted_object(smelted_output, smeltable_object_index, smelt_quantity, section_amounts, turn)
            
            elif event.key == pygame.K_a:
                section_2_row_3[3] +=1
                turn[0]+=50
                print("blocks broken ", str(blocks_broken[0]))
                print("combinations ", str(combinations[0]))
            
            # if any other key is pressed
            else:
                functions.reset_activation(activation)
                activation[crafting]=True
                change_window_size=True
        
        # if the x in the top left corner is pressed, end the game
        if event.type == pygame.QUIT:
            game=False
    
    #################### section requirements ###################
    
    # if you have a crafting table
    if section_1_row_3[2] == True:
        section_2_always_true = True
    # if section 2 is always true and you are in section 1
    if section_2_always_true == True and activation[crafting] == True and activation[water] == False:
        # activate section 2
        activation[water] = True
        change_window_size = True
    # if you have infinite water
    if section_2_row_3[3] == True:
        section_3_always_true = True
    # if section 3 is always true and you are in section 1
    if section_3_always_true == True and activation[crafting] == True and activation[diamond] == False:
        # activate section 3
        activation[diamond] = True
        change_window_size = True
    
    ######################## draw window ######################
    
    # set the window size according to what sections are activated        
    drawing_functions.set_window_size(activation, window_dimensions)
    # if the size needs to be changed, change it
    if change_window_size == True:
        # for the mini menu
        window_dimensions[1] += 30
        window = drawing_functions.init_window(window_dimensions)
        print("size changed")
        change_window_size=False

    # redraw window with white
    window.fill((255,255,255))
    
    ########## draw out the sections if they're activated ########
    
    # if section 0 (Inventory) is activated
    if activation[inventory] == True:
        x=25
        y=35
        drawing_functions.draw_section_boxes(x, y, 3, 2, 0, section_amounts, window)
        drawing_functions.draw_row_seperaters(x, y, 3, 2, window)
        titles=["Tools", "Farming", "Armor",  "Spawners", "Main Area", ""]
        x_offset_for_titles=[30, 20, 30,  15, 15, 0]
        bold = pygame.freetype.Font("Archivo-Bold.ttf", 15)
        drawing_functions.display_names(x, y, section_0_rows_columns[0], section_0_rows_columns[1], titles, x_offset_for_titles, bold, window)
        draw_functions_0=[drawing_functions.draw_diamond_pickaxe_icon, drawing_functions.draw_diamond_hoe_icon, drawing_functions.draw_diamond_armor,  drawing_functions.draw_spawner, drawing_functions.draw_crafting_table, drawing_functions.draw_blank]
        drawing_functions.draw_section_blocks(x, y, 3, 2, draw_functions_0, current_tool, tools, window)
    
    # if section 1 (Crafting) is activated
    if activation[crafting] == True:
        x=25
        y=35
        # all the items that'll be drawn
        draw_functions_1=[drawing_functions.draw_grass, drawing_functions.draw_mushroom, drawing_functions.draw_podzol, drawing_functions.draw_dirt,  drawing_functions.draw_mycelium, drawing_functions.draw_coarse_dirt, drawing_functions.draw_gravel, drawing_functions.draw_flint,  drawing_functions.draw_chest, drawing_functions.draw_wood_planks, drawing_functions.draw_crafting_table, drawing_functions.draw_stick]
        # the names of the items
        titles=["Grass", "Mushroom Block", "Podzol", "Dirt",  "Mycelium", "Coarse Dirt", "Gravel", "Flint",  "Chests", "Wood Planks", "Crafting Tables", "Sticks"]
        x_offset_for_titles=[30, -10, 25, 35,  15, 10, 25, 35,  25, 0, -5, 25]
        names=["Seeds", "Mushrooms", "Podzol", "Dirt",  "Mycelium", "Coarse Dirt", "Gravel", "Flint",  "Chests", "Wood Planks", "Crafting Tables", "Sticks"]
        drawing_functions.draw_section(x, y, crafting-1, section_amounts, section_1_rows_columns[0], section_1_rows_columns[1], draw_functions_1, titles, x_offset_for_titles, names, current_tool, all_tools, time_starting_turns, time_objects, window)
    
    # if section 2 (Water) is activated
    if activation[water] == True:
        x=545
        y=35
        
        cauldron_sayings = ["Empty", "Collected", "Collected", "        Full"]
        cauldron_water = [drawing_functions.draw_blank, drawing_functions.draw_water_lvl_1, drawing_functions.draw_water_lvl_2, drawing_functions.draw_water_lvl_3]
        
        # all the items that'll be drawn
        draw_functions_2=[drawing_functions.draw_coal, drawing_functions.draw_cobblestone, drawing_functions.draw_furnace, drawing_functions.draw_sand,  drawing_functions.draw_glass, drawing_functions.draw_bottle, drawing_functions.draw_iron_ore, drawing_functions.draw_iron_ingot,  ["time object", drawing_functions.draw_cauldron, cauldron_water[section_amounts[1][2][0]] ], drawing_functions.draw_bucket, drawing_functions.draw_water_bucket, drawing_functions.draw_infinite_water]
        # the names of the items
        titles=["Coal", "Cobblestone","Furnace", "Sand",  "Glass", "Bottle", "Iron Ore", "Iron Ingot", "Cauldron", "Bucket", "Water Bucket", "Water Source"]
        x_offset_for_titles=[30, 5, 20, 30,  30, 25, 20, 15,  20, 25, 0, 0]
        names=["Coals", "Cobblestones", "Furnaces", "Sand",  "Glass", "Bottles", "Iron Ores", "Iron Ingots",  cauldron_sayings[section_amounts[1][2][0]], "Buckets", "Water Buckets", "Sources"]
        # draws the section
        drawing_functions.draw_section(x, y, water-1, section_amounts, section_2_rows_columns[0], section_2_rows_columns[1], draw_functions_2, titles, x_offset_for_titles, names, current_tool, all_tools, time_starting_turns, time_objects, window)
    
    # if section 3 (Diamond) is activated
    if activation[diamond] == True:
        x=1065
        y=35
        # all the items that'll be drawn
        draw_functions_3=[drawing_functions.draw_chicken_egg, drawing_functions.draw_witch_egg, drawing_functions.draw_glowstone, drawing_functions.draw_lapis,  drawing_functions.draw_bone, drawing_functions.draw_bone_meal, drawing_functions.draw_dye, drawing_functions.draw_leaves,  drawing_functions.draw_apple, drawing_functions.draw_diamond, drawing_functions.draw_badge, drawing_functions.draw_diamond_badge]
        # the names of the items
        titles=["Egg", "Witch Egg", "Glowstone", "Lapis Lazuli",  "Bone", "Bone Meal", "Light Blue Dye", "Leaves",  "Apple", "DIAMOND!!!", "Badge", "Diamond Badge"]
        x_offset_for_titles=[35, 10, 10, 5,  30, 10, 0, 25,  30, 10, 25, -10]
        names=["Eggs", "Witch Eggs", "Glowstone", "Lapis",  "Bones", "Bone Meal", "Dyes", "Leaves",  "Apples", "DIAMONDS!", "Badges", "Badge 1"]
        # draws the section
        drawing_functions.draw_section(x, y, diamond-1, section_amounts, section_3_rows_columns[0], section_3_rows_columns[1], draw_functions_3, titles, x_offset_for_titles, names, current_tool, all_tools, time_starting_turns, time_objects, window)
    
    # if section 4 (Tools) is activated
    if activation[tools] == True:
        x=25
        y=35
        # all the items that'll be drawn
        draw_functions_4=[drawing_functions.draw_wood_planks, drawing_functions.draw_stick, drawing_functions.draw_cobblestone, drawing_functions.draw_iron_ingot, drawing_functions.draw_diamond,   (drawing_functions.draw_wood_pickaxe, "tool", wood_pickaxe), (drawing_functions.draw_stone_pickaxe, "tool", stone_pickaxe), (drawing_functions.draw_iron_pickaxe, "tool", iron_pickaxe), (drawing_functions.draw_diamond_pickaxe, "tool", diamond_pickaxe), (drawing_functions.draw_wood_sword, "tool", wood_sword),   (drawing_functions.draw_stone_sword, "tool", stone_sword), (drawing_functions.draw_iron_sword, "tool", iron_sword), (drawing_functions.draw_diamond_sword, "tool", diamond_sword), (drawing_functions.draw_bow, "tool", bow), drawing_functions.draw_arrow]
        # the names of the items
        titles=["Wood Plank", "Stick", "Cobblestone", "Iron Ingot", "DIAMOND!!!",  "Wood Pickaxe", "Stone Pickaxe", "Iron Pickaxe", "Diamond Pickaxe", "Wood Sword",  "Stone Sword", "Iron Sword", "Diamond Sword", "Bow", "Arrow"]
        x_offset_for_titles=[10, 30, 5, 15, 5,  0, 0, 5, -15, 5,  5, 10, -5, 35, 30]
        names=["Wood Planks", "Sticks", "Cobblestones", "Iron Ingots", "DIAMONDS!",  "Durability", "Durability", "Durability", "Durability", "Durability",  "Durability", "Durability", "Durability", "Durability", "Arrows"]
        # draws the section
        drawing_functions.draw_section(x, y, tools-1, section_amounts, section_4_rows_columns[0], section_4_rows_columns[1], draw_functions_4, titles, x_offset_for_titles, names, current_tool, all_tools, time_starting_turns, time_objects, window)
    
    # if section 5 (Farming) is activated
    if activation[farming] == True:
        x=25
        y=35
        # all the items that'll be drawn
        
        # farms
        farm_level_sayings = ["Empty", "Stage 1", "Stage 2", "Fully grown"]
        
        draw_wheat_farms = [drawing_functions.draw_farm_lvl_0, drawing_functions.draw_wheat_farm_1, drawing_functions.draw_wheat_farm_2, drawing_functions.draw_wheat_farm_3]
        
        draw_carrot_farms=[drawing_functions.draw_farm_lvl_0, drawing_functions.draw_carrot_farm_1, drawing_functions.draw_carrot_farm_2, drawing_functions.draw_carrot_farm_3]
        
        draw_functions_5=[drawing_functions.draw_wood_planks, drawing_functions.draw_stick, drawing_functions.draw_cobblestone, drawing_functions.draw_iron_ingot, drawing_functions.draw_diamond, drawing_functions.draw_bone, drawing_functions.draw_bone_meal,   (drawing_functions.draw_stone_hoe, "tool", stone_hoe), (drawing_functions.draw_iron_hoe, "tool", iron_hoe), (drawing_functions.draw_diamond_hoe, "tool", diamond_hoe), drawing_functions.draw_dirt, drawing_functions.draw_farm_dirt, drawing_functions.draw_infinite_water, drawing_functions.draw_farm_land,   drawing_functions.draw_grass, ["time object", drawing_functions.draw_farm_dirt, draw_wheat_farms[section_amounts[4][2][1]] ], drawing_functions.draw_wheat, drawing_functions.draw_carrot, ["time object", drawing_functions.draw_farm_dirt, draw_carrot_farms[section_amounts[4][2][4]] ], drawing_functions.draw_sapling, drawing_functions.draw_tree]
        # the names of the items
        titles=["Wood Planks", "Sticks", "Cobblestones", "Iron Ingots", "DIAMONDS!", "Bone", "Bone Meal",  "Stone Hoe", "Iron Hoe", "Diamond Hoe", "Dirt", "Farm Dirt", "Water Source",  "Farm Land", "Grass", "Wheat Farm", "Wheat", "Carrot", "Carrot Farm", "Sapling", "Tree"]
        x_offset_for_titles=[10, 30, 5, 15, 5, 30, 10,  15, 20, 0, 35, 20, 0, 10, 30,  5, 30, 30, 5, 25, 35, 0]
        names=["Wood Planks", "Sticks", "Cobblestones", "Iron Ingots", "DIAMONDS!", "Bones", "Bone Meal",  "Durability", "Durability", "Durability", "Dirt", "Farm Dirt", "Sources", "Plots",  "Seeds", farm_level_sayings[section_amounts[4][2][1]], "Wheat", "Carrots", farm_level_sayings[section_amounts[4][2][4]], "Saplings", "Tree"]
        # draws the section
        drawing_functions.draw_section(x, y, farming-1, section_amounts, section_5_rows_columns[0], section_5_rows_columns[1], draw_functions_5, titles, x_offset_for_titles, names, current_tool, all_tools, time_starting_turns, time_objects, window)
    
    drawing_functions.draw_mini_menu(sections_rows_columns, activation, window, hp, xp_level, hunger, turn, current_tool, all_tools_names)
    
    ####################   time   ######################
    
    functions.check_for_time_object_combination(section_amounts, turn, time_starting_turns, time_objects, how_often)
    
    functions.change_time_object_amounts(section_amounts, turn, time_starting_turns, time_object_limit, time_objects, time_object_section, how_often, activation, window)
    # it also draws the yellow outline
    
    pygame.display.flip()


    
