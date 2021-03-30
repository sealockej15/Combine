"""
drawing_functions

Description:
"""

import functions

black = (0,0,0)
white = (255,255,255)

# for wooden tools
wood_tool_color = (65, 50, 0)
stone_color = (94, 97, 99)
iron_color = (211,211,211)
diamond_color = (0, 255, 255)

wood_color = (54, 44, 13)
water_color = (40,85,255)

# y+=145 because top = 25 box = 100 and bottom = 20

import random, pygame

def set_window_size(activated_sections, window_dimensions):
    if activated_sections[0] == True:
        window_dimensions[0] = 390
        window_dimensions[1] = 290
    if activated_sections[1] == True:
        window_dimensions[0] = 520
        window_dimensions[1] = 435
    if activated_sections[2] == True:
        window_dimensions[0] = 1040
        window_dimensions[1] = 435
    if activated_sections[3] == True:
        window_dimensions[0] = 1560
        window_dimensions[1] = 435
    if activated_sections[4] == True:
        window_dimensions[0] = 650
        window_dimensions[1] = 435
    if activated_sections[5] == True:
        window_dimensions[0] = 910
        window_dimensions[1] = 435
    
def init_window(window_dimensions):
    window=pygame.display.set_mode(window_dimensions)
    window.fill(white)
    return window
    
################### drawing functions ##################

####   drawing functions   ####

# draw a block
def draw_block(x, y, color, window):
    block=pygame.Rect(x, y, 80, 80)
    pygame.draw.rect(window, color, block)

# draw a rectangle
def draw_rectangle(x, y, color, length, height, window):
    rectangle=pygame.Rect(x, y, length, height)
    pygame.draw.rect(window, color, rectangle)

# draw a triangle
def draw_dust(x, y, color, window):
    pygame.draw.polygon(window, color, ((x,y +80), (x +80, y+80), (x +40, y)))

# draw an ellipse
def draw_ellipse(x, y, color, length, height, window):
    ellipse=pygame.Rect(x, y, length, height)
    pygame.draw.ellipse(window, color, ellipse)

# draw an egg
def draw_egg(x, y, color, window):
    draw_ellipse(x+5, y, color, 70, 80, window)

# draw a diamond shape
def draw_gem(x, y, color, window):
    pygame.draw.polygon(window, color, ((x +25,y +2),(x +55,y +2),(x +75,y +37),(x +75,y +62),(x +60,y +77),(x +20,y +77),(x +5,y +62),(x +5,y +37)))

# draws a white square
def draw_blank(x, y, window):
    draw_block(x -1000, y - 1000, white, window)

# draw a badge background
def draw_badge_background(x, y, window):
    frame=pygame.Rect(x, y, 80, 80)
    pygame.draw.rect(window, diamond_color, frame, 5)
    draw_block(x, y, (255, 255, 0), window)
    pygame.draw.polygon(window, (135, 255, 50), ((x,y +65), (x +65,y), (x +80,y), (x +80,y +15), (x +15, y +80), (x, y +80)))
    pygame.draw.polygon(window, (135, 255, 50), ((x,y +15), (x +65,y +80), (x +80,y +80), (x +80,y +65), (x +15, y), (x, y)))

# draws a white/green background
def draw_background(x, y, using, window):
    color=(white)
    if using == True:
        color=(20, 160, 0)
    rim=pygame.Rect(x-3, y-3, 86, 86)
    pygame.draw.rect(window, color, rim, 5)

# draws the boxes around the blocks

def draw_section_boxes(x, y, max_columns, max_rows, section_number, amounts, window):
    x-=10
    y-=10
    row = 0
    while row < max_rows:
        column = 0
        while column < max_columns:
            # the amount would only be "" if the spot is supposed to be blank
            if str(amounts[section_number][row][column]) != "":
                box=pygame.Rect(x, y, 100, 100)
                pygame.draw.rect(window, black, box, 3)
            x+=130
            column+=1
        row+=1
        x-=130 *max_columns
        y+=145
        
# draws the seperating lines

def draw_row_seperaters(x, y, max_columns, max_rows, window):
    x-=25
    y-=35
    row=1
    while row <= max_rows:
        pygame.draw.line(window, black, (x, y +(row *145)), (x +(max_columns *130), y +(row *145)), 3)
        row+=1

# displays the block names
def display_names(x, y, max_columns, max_rows, titles, offset, bold, window):
    x-=10
    y-=30
    row = 0
    while row < max_rows:
        column = 0
        while column < max_columns:
            bold.render_to(window, (x +offset[column +(row*max_columns)], y), titles[column +(row *max_columns)])
            x+=130
            column+=1
        row+=1
        x-=130 *max_columns
        y+=145

# display the item name and how many you have
def names_and_amount(x, y, max_columns, max_rows, names, all_resource_amounts, section, font, time_starting_turns, time_objects, window):
    x-=10
    y+=92
    row = 0
    while row < max_rows:
        column = 0
        # to make sure if it has different stages
        time_sayings = ["Empty", "Stage 1", "Stage 2", "Fully grown", "        Full"]
        
        while column < max_columns:
            if type(all_resource_amounts[section][row][column]) == list:
                # if it's a tool
                if all_resource_amounts[section][row][column][0] == "tool":
                    font.render_to(window, (x-5, y), names[column +(row *max_columns)] +":  " +str(all_resource_amounts[section][row][column][1]) +" / " +str(all_resource_amounts[section][row][column][2]))
                # if it's in multiple different sections
                elif all_resource_amounts[section][row][column][0] == "reference":
                    font.render_to(window, (x, y), names[column +(row *max_columns)] +": " +str(all_resource_amounts[all_resource_amounts[section][row][column][1]][all_resource_amounts[section][row][column][2]][all_resource_amounts[section][row][column][3]]))
                # if the resource had to be first mined
                elif all_resource_amounts[section][row][column][0] == "mineable":
                    font.render_to(window, (x, y), "Mined: " +str(all_resource_amounts[section][row][column][1]) +" / " +str(all_resource_amounts[section][row][column][2]))
                # if it's in a different section AND has to be mined
                elif all_resource_amounts[section][row][column][0] == "refer and mine":
                    font.render_to(window, (x, y), "Mined: " +str(all_resource_amounts[all_resource_amounts[section][row][column][1]][all_resource_amounts[section][row][column][2]][all_resource_amounts[section][row][column][3]][1]) +" / " +str(all_resource_amounts[all_resource_amounts[section][row][column][1]][all_resource_amounts[section][row][column][2]][all_resource_amounts[section][row][column][3]][2]))
            # if it has multiple stages
            elif names[column +(row *max_columns)] in time_sayings:
                counter = functions.get_section_index((section,row,column), time_objects)
                # if it's a cauldron
                if time_objects[counter] == time_objects[0]:
                    font.render_to(window, (x, y), names[column +(row *max_columns)])
                elif time_starting_turns[counter][0] == True and all_resource_amounts[time_objects[counter][0]][time_objects[counter][1]][time_objects[counter][2]] == 0: 
                    font.render_to(window, (x, y), "Stage 0")
                else:
                    font.render_to(window, (x, y), names[column +(row *max_columns)])
            # the amount would only be "" if the spot is supposed to be blank
            elif str(all_resource_amounts[section][row][column]) != "":
                font.render_to(window, (x, y), names[column +(row *max_columns)] +": " +str(all_resource_amounts[section][row][column]))
            x+=130
            column+=1
        row+=1
        x-=130 *max_columns
        y+=145

# draws all blocks in a section 
def draw_section_blocks(x, y, max_columns, max_rows, functions, current_tool, tools, window):
    row = 0
    while row < max_rows:
        column = 0
        while column < max_columns:
            if type(functions[column +(row *max_columns)]) == tuple:
                if functions[column +(row *max_columns)][1] == "tool":
                    using = False
                    if current_tool == tools[functions[column +(row *max_columns)][2]]:
                        using = True
                    functions[column +(row *max_columns)][0](x, y, using, window)
            elif type(functions[column +(row *max_columns)]) == list and functions[column +(row *max_columns)][0] == "time object":
                # draw the base
                functions[column +(row *max_columns)][1](x, y, window)
                # draw the changeable part
                functions[column +(row *max_columns)][2](x, y, window)
            else:
                functions[column +(row *max_columns)](x, y, window)
            column+=1
            x+=130
        row+=1
        x-=130 *max_columns
        y+=145

# draw a section
def draw_section(x, y, section_number, all_resource_amounts, columns, rows, draw_functions, titles, x_offset_for_titles, names, current_tool, tools, time_starting_turns, time_objects, window):
    font = pygame.freetype.Font("Archivo-Regular.ttf", 15)
    bold = pygame.freetype.Font("Archivo-Bold.ttf", 15)
    draw_section_blocks(x, y, columns, rows, draw_functions, current_tool, tools, window)
    draw_section_boxes(x, y, columns, rows, section_number, all_resource_amounts, window)
    draw_row_seperaters(x, y, columns, rows, window)
    pygame.draw.line(window, black, (x -25 +130 *columns,0), (x -25 +130 *columns,145 *rows), 5)
    display_names(x, y, columns, rows, titles, x_offset_for_titles, bold, window)
    names_and_amount(x, y, columns, rows, names, all_resource_amounts, section_number, font, time_starting_turns, time_objects, window)    



#######################   mini menu   ########################


def draw_mini_menu(sections_rows_columns, activation, window, hp, xp_level, hunger, turn, current_tool, tool_names):
    font = pygame.freetype.Font("Archivo-Regular.ttf", 15)
    bold = pygame.freetype.Font("Archivo-Bold.ttf", 15)
    counter = 0
    while counter < len(activation):
        if activation[counter] == True:
            break
        counter += 1
    # y = 145 times the amount of rows in that section
    y = 145 *sections_rows_columns[counter][1]
    bold.render_to(window, (10, y +11), "HP: " +str(hp[0]))
    bold.render_to(window, (75, y +10), "Hunger: " +str(hunger[0]) +"/20")
    bold.render_to(window, (190, y +10), "Lvl: " +str(xp_level[0]))
    bold.render_to(window, (240, y +11), "Turn: " +str(turn[0]))
    bold.render_to(window, (325, y +10), "Tool: " +str(tool_names[current_tool]))


#######################   section 0 (inventory)   ##################



def draw_diamond_hoe_icon(x, y, window):
    using=False
    draw_diamond_hoe(x, y, using, window)
def draw_diamond_pickaxe_icon(x, y, window):
    using=False
    draw_diamond_pickaxe(x, y, using, window)



########################   section 1 (crafting)   #########################



# dirt
def draw_dirt(x, y, window):
    dirt=pygame.Rect(x, y, 80, 80)
    pygame.draw.rect(window, (104, 83, 59), dirt)

# all of the blocks
def get_grass_coordinates():
    coordinates=[]
    while len(coordinates) != 8:
        coordinates.append(random.randint(0, 30))
    return coordinates

def draw_grass(x, y, window):
    grass_coordinates=[15, 22, 12, 19, 3, 16, 10, 28]
    pygame.draw.line(window, (67, 132, 29), (x, y +80), (x +80, y +80), 5)
    counter = 0
    while counter < 8:
        pygame.draw.line(window, (67, 132, 29), (x +5 +(counter *10),y +80), (x +5 +(counter *10),y +grass_coordinates[counter]),5)
        counter+=1

def draw_mushroom(x, y, window):
    draw_block(x, y , (193, 165, 133), window)

def draw_podzol(x, y, window):
    draw_dirt(x, y, window)
    draw_rectangle(x, y, (94, 53, 7), 80, 20, window)

def draw_mycelium(x, y, window):
    draw_dirt(x, y, window)
    draw_rectangle(x, y, (120, 113, 130), 80, 20, window)

def draw_coarse_dirt(x, y, window):
    draw_block(x, y, (79, 57, 3), window)

def draw_gravel(x, y, window):
    draw_block(x, y, (125,128,132), window)

def draw_flint(x, y, window):
    pygame.draw.polygon(window, black, ((x, y), (x, y +80), (x +80, y +80)))

def draw_chest(x, y, window):
    draw_block(x, y, (107, 83, 22), window)
    draw_rectangle(x, y +25, black, 80, 10, window)
    draw_rectangle(x +27, y +15, black, 25, 30, window)
    draw_rectangle(x +30, y +18, (237,237,237), 19, 24, window)

def draw_wood_planks(x, y, window):
    draw_block(x, y, (160, 140, 80), window)
    counter = 0
    while counter < 4:
        pygame.draw.line(window, (0,0,0), (x, y +10 + counter *20), (x +80, y +10 + counter *20), 3)
        counter+=1

def draw_crafting_table(x, y, window):
    draw_block(x, y, (73, 54, 2), window)
    pygame.draw.line(window, black, (x, y +int(80/3)),(x +80, y +int(80/3)),3)
    pygame.draw.line(window, black, (x, y +int(80/3 *2)),(x +80, y +int(80/3 *2)),3)
    pygame.draw.line(window, black, (x +int(80/3), y),(x +int(80/3), y +80),3)
    pygame.draw.line(window, black, (x +int(80/3 *2), y),(x +int(80/3 *2), y +80),3)    

def draw_stick(x, y, window):
    draw_rectangle(x+30, y, wood_color, 20, 80, window)



######################   section 2 (water)   #####################



# draws all blocks in section 2
def draw_coal(x, y, window):
    draw_dust(x, y, black, window)

def draw_cobblestone(x, y, window):
    draw_block(x, y, (94, 97, 99), window)

def draw_furnace(x, y, window):
    draw_block(x, y, (68, 68, 68), window)
    draw_rectangle(x +17, y +40, (255, 110, 0), 45, 25, window)

def draw_sand(x, y, window):
    draw_block(x, y, (255, 255, 0), window)

def draw_glass(x, y, window):
    draw_block(x, y, (215, 227, 247), window)
    draw_rectangle(x+2, y+2, (239, 243, 249), 76, 76, window)

def draw_bottle(x, y, window):
    pygame.draw.polygon(window, (215, 227, 247), ((x +20,y),(x +60,y),(x +60,y +30),(x +70,y +30),(x +70,y +80),(x +10,y +80),(x +10,y +30),(x +20,y +30)), 5)
    draw_rectangle(x +22, y +2, (170, 145, 107), 36, 31, window)   
    
def draw_iron_ore(x, y, window):
    iron_coordinates=[(5, 28), (10, 14), (15, 56), (25, 39), (35, 5), (35, 28), (40, 65), (45, 53), (55, 34), (65, 12), (65, 64)]
    draw_block(x, y, (94, 97, 99), window)
    while len(iron_coordinates) > 0:
        draw_rectangle(x +iron_coordinates[len(iron_coordinates)-1][0], y +iron_coordinates[len(iron_coordinates)-1][1], (225,210,150), 10, 10, window)
        del iron_coordinates[len(iron_coordinates)-1]

def draw_iron_ingot(x, y, window):
    draw_rectangle(x, y +25, iron_color, 80, 30, window)

def draw_cauldron(x, y, window):
    pygame.draw.polygon(window, iron_color, ((x,y), (x +15, y), (x +15,y +15), (x +65,y +15), (x +65,y), (x +80,y), (x +80, y +80), (x,y +80)))


def draw_water_lvl_1(x, y, window):
    pygame.draw.polygon(window, water_color, ((x +15,y +15), (x +65, y +15), (x +65, y +20), (x +15, y +20)))

def draw_water_lvl_2(x, y, window):
    pygame.draw.polygon(window, water_color, ((x +15,y +10), (x +65, y +10), (x +65, y +20), (x +15, y +20)))

def draw_water_lvl_3(x, y, window):
    pygame.draw.polygon(window, water_color, ((x +15,y +5), (x +65, y +5), (x +65, y +20), (x +15, y +20)))


def draw_bucket(x, y, window):
    pygame.draw.polygon(window, iron_color, ((x +10,y +5), (x +10,y +45), (x +20,y +70), (x +60,y +70), (x +70,y +45), (x +70,y +5), (x +70,y +45), (x +60,y +70), (x +20,y +70), (x +10,y +45)), 10)

def draw_water_bucket(x, y, window):
    draw_bucket(x, y, window)
    pygame.draw.polygon(window, water_color, ((x +15,y +10), (x +15,y +42), (x +23,y +65), (x +57,y +65), (x +65,y +42), (x +65,y +10)))

def draw_infinite_water(x, y, window):
    draw_rectangle(x-5, y-5, water_color, 90, 90, window)



###########################   section 3 (diamond)   #######################



def draw_chicken_egg(x, y, window):
    draw_egg(x, y, (216, 215, 164), window)

def draw_witch_egg(x, y, window):
    draw_egg(x, y, (100,0,100), window)

def draw_glowstone(x, y, window):
    draw_dust(x, y, (255, 255, 0), window)

def draw_lapis(x, y, window):
    draw_gem(x, y, (0,75,200), window)

def draw_bone(x, y, window):
    draw_rectangle(x +30, y, (240, 240, 240), 20, 80, window)

def draw_bone_meal(x, y, window):
    draw_ellipse(x, y, (240,240,240), 80, 80, window)

def draw_dye(x, y, window):
    draw_ellipse(x +10, y +20, (60, 160, 190), 60, 40, window)

def draw_leaves(x, y, window):
    draw_block(x, y, (28, 132, 18), window)

def draw_apple(x, y, window):
    draw_ellipse(x, y, (255, 0, 0), 80, 80, window)

def draw_diamond(x, y, window):
    draw_gem(x, y, diamond_color, window)

def draw_badge(x, y, window):
    draw_badge_background(x, y, window)

def draw_diamond_badge(x, y, window):
    draw_badge_background(x, y, window)
    #  smaller diamond
    pygame.draw.polygon(window, diamond_color, ((x +30,y +7),(x +50,y +7),(x +70,y +37),(x +70,y +57),(x +55,y +72),(x +25,y +72),(x +10,y +57),(x +10,y +37)))
    


############################    section 4 (tools)    ########################



def draw_pickaxe(x, y, color, using, window):
    draw_background(x, y, using, window)
    pygame.draw.polygon(window, wood_color, ((x +12,y +80), (x +60, y +30), (x +50, y +20), (x +10, y +65)))
    pygame.draw.polygon(window, color, ((x+50, y+20), (x +65, y +35), (x +65, y +50), (x +70, y +50), (x +75, y +30), (x +50, y+5), (x +30, y +10), (x +30, y +15), (x +45, y +15)))
    
def draw_wood_pickaxe(x, y, using, window):
    draw_pickaxe(x, y, wood_tool_color, using, window)

def draw_stone_pickaxe(x, y, using, window):
    draw_pickaxe(x, y, stone_color, using, window)

def draw_iron_pickaxe(x, y, using, window):
    draw_pickaxe(x, y, iron_color, using, window)

def draw_diamond_pickaxe(x, y, using, window):
    draw_pickaxe(x, y, diamond_color, using, window)

def draw_sword(x, y, color, using, window):
    draw_background(x, y, using, window)
    pygame.draw.polygon(window, wood_color, ((x +17,y +75), (x +30, y +55), (x +23, y +50), (x +15, y +65)))
    pygame.draw.polygon(window, color, ((x +30, y +55), (x +37, y +60), (x +47, y +57), (x +16, y +35), (x +16, y +45)))
    pygame.draw.polygon(window, color, ((x +35, y +50), (x +60, y +10), (x +50, y +10), (x +25, y +45)))
    pygame.draw.line(window, wood_color, (x +37, y +50), (x +25, y +41), 3)

def draw_wood_sword(x, y, using, window):
    draw_sword(x, y, wood_tool_color, using, window)

def draw_stone_sword(x, y, using, window):
    draw_sword(x, y, stone_color, using, window)
    
def draw_iron_sword(x, y, using, window):
    draw_sword(x, y, iron_color, using, window)

def draw_diamond_sword(x, y, using, window):
    draw_sword(x, y, diamond_color, using, window)

def draw_bow(x, y, using, window):
    Bow=pygame.Rect(x +15, y +5, 50, 70)
    pygame.draw.ellipse(window, wood_color, Bow, 5)
    draw_rectangle(x -25, y, white, 60, 80, window)
    pygame.draw.line(window, (100, 100, 100), (x +35, y +2), (x +35, y +78), 5)
    draw_background(x, y, using, window)

def draw_arrow(x, y, window):
    pygame.draw.line(window, wood_color, (x +15, y +65), (x +65, y +15), 5)
    pygame.draw.polygon(window, (105, 105, 105), ((x +45, y +20), (x +65, y +30), (x +70, y +10)))
    pygame.draw.polygon(window, black, ((x +10, y +60), (x +20, y +60), (x +20, y +70), (x +13, y +78), (x +13, y +68), (x +3, y +68)), 2)
    pygame.draw.polygon(window, white, ((x +10, y +60), (x +20, y +60), (x +20, y +70), (x +13, y +78), (x +13, y +68), (x +3, y +68)))



############################   section 5 (farming)   #################



def draw_hoe(x, y, color, using, window):
    draw_background(x, y, using, window)
    pygame.draw.polygon(window, wood_color, ((x +12,y +80), (x +60, y +30), (x +50, y +25), (x +10, y +70)))
    pygame.draw.polygon(window, color, ((x +60,y +30), (x +65, y +32), (x +70, y +25), (x +40, y +5), (x +30, y +5), (x +20, y +10), (x +17, y +20), (x +33, y +15)))

def draw_farm_dirt(x, y, window):
    draw_dirt(x, y, window)
    counter = 0
    while counter < 4:
        counter_2 = 0
        while counter_2 < 8:
            pygame.draw.polygon(window, (90, 50, 10), ((x +counter_2*10, y +15 +(counter *18)), (x +5 +counter_2*10, y +12 +(counter *18)), (x +10 +counter_2*10, y +15 +(counter *18)), (x +5 +counter_2*10, y +12 +(counter *18))), 5)
            counter_2+=1
        counter+=1
    white_rim=pygame.Rect(x-1, y-1, 82, 82)
    pygame.draw.rect(window, white, white_rim, 2)

def draw_stone_hoe(x, y, using, window):
    draw_hoe(x, y, stone_color, using, window)
    
def draw_iron_hoe(x, y, using, window):
    draw_hoe(x, y, iron_color, using, window)

def draw_diamond_hoe(x, y, using, window):
    draw_hoe(x, y, diamond_color, using, window)
    
def draw_farm_land(x, y, window):
    draw_farm_dirt(x, y, window)
    counter = 1
    while counter <= 4:
        pygame.draw.line(window, (104, 83, 59), (x, y + counter *18), (x + 80, y +counter *18), 5)
        counter+=1
    draw_rectangle(x +25, y +25, water_color, 30, 30, window)

def draw_farm_lvl_0(x, y, window):
    counter = 0
    while counter < 4:
        counter_2 = 1
        while counter_2 < 8:
            # so that it doesn't peak above the water
            if counter >= 1 and counter <= 2 and counter_2 >= 3 and counter_2 <= 5:
                counter_2+=1
                continue
            pygame.draw.line(window, (100,200,0), (x +counter_2*10, y +12 +(counter *18)), (x +counter_2*10, y +11 +(counter *18)), 2)
            counter_2 +=1
            # to cover up a part
        pygame.draw.line(window, (104, 83, 59), (x, y + (counter +1) *18), (x + 80, y +(counter +1) *18), 5)
        counter+=1
    draw_rectangle(x +25, y +25, water_color, 30, 30, window)

def draw_wheat_farm_1(x, y, window):
    counter = 0
    while counter < 4:
        counter_2 = 1
        while counter_2 < 8:
            # so that it doesn't peak above the water
            if counter >= 1 and counter <= 2 and counter_2 >= 3 and counter_2 <= 5:
                counter_2+=1
                continue
            pygame.draw.line(window, (100,200,0), (x +counter_2*10, y +12 +(counter *18)), (x +counter_2*10, y +9 +(counter *18)), 2)
            counter_2 +=1
            # to cover up a part
        pygame.draw.line(window, (104, 83, 59), (x, y + (counter +1) *18), (x + 80, y +(counter +1) *18), 5)
        counter+=1
    draw_rectangle(x +25, y +25, water_color, 30, 30, window)

def draw_wheat_farm_2(x, y, window):
    # draw the original, but make the wheat longer and yellower
    draw_wheat_farm_1(x, y, window)
    counter = 0
    while counter < 4:
        counter_2 = 1
        while counter_2 < 8:
            # so that it doesn't peak above the water
            if counter >= 1 and counter <= 2 and counter_2 >= 3 and counter_2 <= 5:
                counter_2+=1
                continue
            pygame.draw.line(window, (150,200,0), (x +counter_2*10, y +12 +(counter *18)), (x +counter_2*10, y +5 +(counter *18)), 2)
            counter_2 +=1
        counter+=1

def draw_wheat_farm_3(x, y, window):
    # draw the original, but make the wheat longer and yellower
    draw_wheat_farm_1(x, y, window)
    counter = 0
    while counter < 4:
        counter_2 = 1
        while counter_2 < 8:
            # so that it doesn't peak above the water
            if counter >= 1 and counter <= 2 and counter_2 >= 3 and counter_2 <= 5:
                counter_2+=1
                continue
            pygame.draw.line(window, (200,200,50), (x +counter_2*10, y +12 +(counter *18)), (x +counter_2*10, y +3 +(counter *18)), 1)
            pygame.draw.line(window, (200,200,50), (x +counter_2*10, y +10 +(counter *18)), (x +2 +counter_2*10, y +5 +(counter *18)), 1)
            pygame.draw.line(window, (200,200,50), (x +counter_2*10, y +10 +(counter *18)), (x -2 +counter_2*10, y +5 +(counter *18)), 1)
            counter_2 +=1
        counter+=1

def draw_wheat(x, y, window):
    counter = 0
    while counter < 10:
        if counter % 2 == 0:
            color =(200,175,0)
        else:
            color = (200, 200, 0)
        pygame.draw.line(window, color, (x +30 +counter*2,y +75), (x +30 + counter*2, y +45), 2)
        pygame.draw.line(window, color, (x +30 +counter*2,y +45), (x +20 + counter*4, y +5), 2)
        counter+=1
    # band holding the wheat together
    pygame.draw.line(window, (125,25,0), (x +29, y +45), (x +49, y +45), 3)
    pygame.draw.line(window, (175,50,0), (x +29, y +87/2), (x +49, y +87/2), 2)
    pygame.draw.line(window, (125,25,0), (x +29 ,y +42), (x +49, y +42), 2)

def draw_carrot(x, y, window):
    pygame.draw.line(window, (0,200,0), (x +30, y+14), (x +50, y+14), 3)
    counter = 0
    while counter < 7:
        pygame.draw.line(window, (0,200,0), (x +28 +counter*4, y+5), (x +40, y+15), 2)
        counter+=1
    pygame.draw.polygon(window, (250,150,25), ((x +40, y +75), (x +25, y +15), (x +55, y +15)))

def draw_carrot_farm_1(x, y, window):
    counter = 0
    while counter < 4:
        counter_2 = 1
        while counter_2 < 8:
            # so that it doesn't peak above the water
            if counter >= 1 and counter <= 2 and counter_2 >= 3 and counter_2 <= 5:
                counter_2+=1
                continue
            pygame.draw.line(window, (0,200,0), (x +counter_2*10, y +12 +(counter *18)), (x +2 +counter_2*10, y +9 +(counter *18)), 1)
            pygame.draw.line(window, (0,200,0), (x +counter_2*10, y +12 +(counter *18)), (x -2 +counter_2*10, y +9 +(counter *18)), 1)
            counter_2 +=1
        # to cover up a part
        pygame.draw.line(window, (104, 83, 59), (x, y + (counter +1) *18), (x + 80, y +(counter +1) *18), 5)
        counter+=1
    draw_rectangle(x +25, y +25, water_color, 30, 30, window)

def draw_carrot_farm_2(x, y, window):
    counter = 0
    while counter < 4:
        counter_2 = 1
        while counter_2 < 8:
            # so that it doesn't peak above the water
            if counter >= 1 and counter <= 2 and counter_2 >= 3 and counter_2 <= 5:
                counter_2+=1
                continue
            pygame.draw.line(window, (0,200,0), (x +counter_2*10, y +12 +(counter *18)), (x +2 +counter_2*10, y +7 +(counter *18)), 1)
            pygame.draw.line(window, (0,200,0), (x +counter_2*10, y +12 +(counter *18)), (x -2 +counter_2*10, y +7 +(counter *18)), 1)
            counter_2 +=1
        # to cover up a part
        pygame.draw.line(window, (104, 83, 59), (x, y + (counter +1) *18), (x + 80, y +(counter +1) *18), 5)
        counter+=1
    draw_rectangle(x +25, y +25, water_color, 30, 30, window)    

def draw_carrot_farm_3(x, y, window):
    counter = 0
    while counter < 4:
        counter_2 = 1
        while counter_2 < 8:
            # so that it doesn't peak above the water
            if counter >= 1 and counter <= 2 and counter_2 >= 3 and counter_2 <= 5:
                counter_2+=1
                continue
            pygame.draw.line(window, (250,150,25), (x +counter_2*10, y +12 +(counter *18)), (x +counter_2*10, y +10 +(counter *18)), 3)
            pygame.draw.line(window, (0,200,0), (x +counter_2*10, y +10 +(counter *18)), (x +2 +counter_2*10, y +5 +(counter *18)), 1)
            pygame.draw.line(window, (0,200,0), (x +counter_2*10, y +10 +(counter *18)), (x -2 +counter_2*10, y +5 +(counter *18)), 1)
            counter_2 +=1
        # to cover up a part
        pygame.draw.line(window, (104, 83, 59), (x, y + (counter +1) *18), (x + 80, y +(counter +1) *18), 5)
        counter+=1
    draw_rectangle(x +25, y +25, water_color, 30, 30, window) 

def draw_sapling(x, y, window):
    pygame.draw.line(window, (60,50,0), (x +40, y +75),(x +40, y +60), 10)
    draw_rectangle(x +25, y +40, (28, 132, 18), 30, 20, window)

def draw_tree(x, y, window):
    draw_rectangle(x +32, y +70, (104, 83, 59), 16, 15, window)
    draw_rectangle(x +32, y +15, (60,50,0), 16, 55, window)
    pygame.draw.polygon(window, (28, 132, 18), ((x +15, y +48), (x +65, y +48), (x +65, y +18), (x +55, y +18), (x +55, y +5), (x +25, y +5), (x +25, y +18), (x +15, y +18)))
    
    


###########################   section 6 (armor)   ######################



def draw_armor(x, y, color, window):
    pygame.draw.polygon(window, color, ((x +5,y +20),(x +15,y +5),(x +25,y +5),(x +35,y +25),(x +45,y +25),(x +55,y +5),(x +65,y +5),(x +75,y +20),(x +75,y +30),(x +65,y +50),(x +60,y +70),(x +50,y +75),(x +30,y +75),(x +20,y +70),(x +15,y +50),(x +5,y +30)))

def draw_diamond_armor(x, y, window):
    draw_armor(x, y, diamond_color, window)



####################   section 7 (spawners)   ##################



def draw_spawner(x, y, window):
    pygame.draw.polygon(window, (50, 50, 50), ((x, y), (x +80, y), (x +80, y +80), (x, y +80)), 3)
    counter=0
    while counter < 4:
        pygame.draw.line(window, (50, 50, 50), (x, y +16 +counter *16), (x +80, y +16 +counter *16), 3)
        pygame.draw.line(window, (50, 50, 50), (x +16 +counter *16, y), (x +16 +counter *16, y +80), 3)
        counter+=1
