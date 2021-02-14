#Original
# Jalen: 499
# Max: 695


# to be added
redstone=0
gunpowder=0
# edit witch drops
# edit leaves drops
# spawner code 
"""
if int(turn/7) == turn/7:
    effect
"""

# started January 8th  finished to trophy February 10th
"""
Combine_2

Description:
"""
import pygame, random, tsk, pygame.freetype
pygame.init()

#screen
window=pygame.display.set_mode([1560,440])
window.fill((255,255,255))

game=True
turns=0
font = pygame.freetype.Font("Archivo-Regular.ttf", 15)
bold = pygame.freetype.Font("Archivo-Bold.ttf", 15)

# titles (bold)
itemTitlesRow1=["Grass", "Mushroom Block","Podzol", "Dirt", "Leaves", "Apple", "Egg", "Coal", "Glowstone", "Water Bucket", "Light Blue Dye", "VICTORY!!!"]
itemTitlesRow2=["Mycelium", "Coarse Dirt", "Gravel", "Flint", "Cobblestone", "Furnace", "Sand", "Glass Block", "Witch Egg", "Bucket", "Lapis Lazuli", "Armor"]
itemTitlesRow3=["Chest", "Wood Plank", "Crafting Table", "Stick", "Bottle", "Iron Ore", "Iron Ingot", "Bone", "Bone Meal", "Cauldron", "Water Source", "DIAMOND!!!"]
itemTitlesRows=[itemTitlesRow1, itemTitlesRow2, itemTitlesRow3]
# names
itemNamesRow1=["Seeds", "Mushrooms", "Podzol", "Dirt", "Leaves", "Apples", "Eggs", "Coal", "Glowstone", "Water Buckets", "Dyes", "WINS"]
itemNamesRow2=["Mycelium", "Coarse Dirt", "Gravel", "Flint", "Cobblestone", "Furnaces", "Sand", "Glass", "Witch Egg", "Buckets", "Lapis Lazuli", "Armor Sets"]
itemNamesRow3=["Chests", "Wood Planks", "Crafting Tables", "Sticks", "Bottles", "Iron Ore", "Iron Ingots", "Bones", "Bone Meal", "Water", "INFINITE", "DIAMONDS"]
itemNamesRows=[itemNamesRow1, itemNamesRow2, itemNamesRow3]
# list of amounts
itemVariablesRow1=[50,50,0,0,0,0,0,0,0,0,0,0]
itemVariablesRow2=[0,0,0,0,0,0,0,0,0,0,0,0]
itemVariablesRow3=[0,0,0,0,0,0,0,0,0,0,0,0]
itemVariablesRows=[itemVariablesRow1, itemVariablesRow2, itemVariablesRow3]
# centering the titles
xOffsetRow1=[-90, -120, -90, -80, -90, -85, -80, -80, -100, -115, -115, -105]
xOffsetRow2=[-100, -105, -90, -80, -110, -95, -85, -110, -105, -90, -110, -90]
xOffsetRow3=[-85, -110, -115, -85, -85, -95, -100, -90, -105, -110, -110, -110]
xOffsetRows=[xOffsetRow1, xOffsetRow2, xOffsetRow3]

############## Items ##############

# Row 1
counter=0
grass=[]
while counter != 8:
    grass.append(random.randint(50,80))
    counter+=1
mushroom_block=pygame.Rect(155,325,80,80)
podzol_top=pygame.Rect(285,325,80,20)
podzol_dirt=pygame.Rect(285,325,80,80)
dirt_block=pygame.Rect(415,325,80,80)
leaf_block=pygame.Rect(545,325,80,80)
apple=pygame.Rect(675,325,80,80)
egg=pygame.Rect(810,325,70,80)
coal=[(935,405),(975,325),(1015,405)]
glowstone=[(1065,405),(1105,325),(1145,405)]
bucket_1=[(1205,330), (1205,370), (1215,395), (1255,395), (1265,370), (1265,330), (1265,370), (1255,395), (1215,395), (1210,365)]
water_bucket=[(1210,335), (1210,365), (1220,390), (1250,390), (1260,365), (1260,335)]
dye=pygame.Rect(1335,345,60,40)
Row_1_rects=[mushroom_block, podzol_dirt, podzol_top, dirt_block, leaf_block, apple, egg, coal, glowstone, bucket_1, water_bucket, dye]
Row_1_colors=[(193, 165, 133), (104, 83, 59), (94, 53, 7), (104, 83, 59), (28, 132, 18), (255,0,0), (216, 215, 164), (0,0,0),(255,255,0), (211,211,211), (40,85,255), (60,160,190)]
# Row 2
mycelium_top=pygame.Rect(25,180,80,20)
mycelium_dirt=pygame.Rect(25,180,80,80)
coarse_dirt=pygame.Rect(155,180,80,80)
gravel_block=pygame.Rect(285,180,80,80)
flint=[(420,260),(495,180),(495,260)]
cobble_block=pygame.Rect(545,180,80,80)
furnace_block=pygame.Rect(675,180,80,80)
furnace_fire=pygame.Rect(692,220,45,25)
sand_block=pygame.Rect(805,180,80,80)
glass_block=pygame.Rect(935,180,80,80)
glass_rim=pygame.Rect(935,180,80,80)
witch_egg=pygame.Rect(1070,180,70,80)
bucket_2=[(1205,185), (1205,225), (1215,250), (1255,250), (1265,225), (1265,185), (1265,225), (1255,250), (1215,250), (1205,225)]
lapis=[(1350,182),(1380,182),(1400,217),(1400,242),(1385,257),(1345,257),(1330,242),(1330,217)]
diamond_armor=[(1460,200),(1470,185),(1480,185),(1490,205),(1500,205),(1510,185),(1520,185),(1530,200),(1530,210),(1520,230),(1515,250),(1505,255),(1485,255),(1475,250),(1470,230),(1460,210)]
Row_2_rects=[mycelium_dirt, mycelium_top, coarse_dirt, gravel_block, flint, cobble_block, furnace_block, furnace_fire, sand_block, glass_rim, glass_block, witch_egg, bucket_2, lapis, diamond_armor]
Row_2_colors=[(104, 83, 59), (120, 113, 130), (79, 57, 3), (125,128,132), (0,0,0), (94, 97, 99), (68, 68, 68), (255, 110, 0),(255,255,0), (215, 227, 247), (239, 243, 249),(100,0,100), (211,211,211), (0,75,200), (0,255,255)]
# Row 3
chest_block=pygame.Rect(25,35,80,80)
chest_line=pygame.Rect(25,60,80,10)
chest_opener_outline=pygame.Rect(52,50,25,30)
chest_opener=pygame.Rect(55,53,19,24)
wood_plank_block=pygame.Rect(155,35,80,80)
crafting_table_block=pygame.Rect(285,35,80,80)
stick=pygame.Rect(445,35,20,80)
bottle=((565,35),(605,35),(605,65),(615,65),(615,115),(555,115),(555,65),(565,65))
bottle_cork=pygame.Rect(567,37,36,31)
iron_ore=pygame.Rect(675,35,80,80)
iron=[]

counter=0
while counter != 7:
    iron.append(680 +counter*10)
    iron.append(random.randint(40,100))
    iron.append(680 +counter*10)
    iron.append(random.randint(40,100))
    counter+=1
iron_ingot=pygame.Rect(805,60,80,30)
bone=pygame.Rect(965,35,20,80)
bone_meal=pygame.Rect(1065,35,80,80)
cauldron=[(1195,35), (1210, 35), (1210,50), (1260,50), (1260,35), (1275,35), (1275, 115), (1195,115)]
cauldron_true=False
infinite_water=pygame.Rect(1318, 28, 94,94)
diamond=[(1480,37),(1510,37),(1530,72),(1530,97),(1515,112),(1475,112),(1460,97),(1460,72)]
Row_3_rects=[chest_block, chest_line, chest_opener_outline, chest_opener, wood_plank_block, crafting_table_block, stick, bottle, bottle_cork, iron_ore, iron_ingot, bone, bone_meal, cauldron, infinite_water, diamond]
Row_3_colors=[(107, 83, 22),(0,0,0),(0,0,0),(237,237,237), (160, 140, 80), (73, 54, 2), (56, 44, 13), (215, 227, 247), (170, 145, 107), (105, 109, 105), (211,211,211), (240,240,240), (240,240,240), (200,200,200), (40,85,255), (0,255,255)]

Row_rects=[Row_1_rects, Row_2_rects, Row_3_rects]
Row_colors=[Row_1_colors, Row_2_colors, Row_3_colors]

ellipses=[apple, egg, bone_meal, witch_egg, dye]
polygons=[coal, flint, bottle, glowstone, cauldron, water_bucket, lapis, diamond, diamond_armor]

    ######################## Combinations ###########################

# If it can be combined
Row1_options=["grass","mushroom","podzol","dirt","leaves","apple","egg","coal", "glowstone", "water bucket", "dye", "victory"]
Row2_options=["mycelium","coarse dirt","gravel","flint","cobblestone","furnace","sand","glass", "witch egg", "bucket", "lapis", "armor"]
Row3_options=["chest","wood plank","crafting table","stick","bottle","iron ore","iron ingot","bone", "bone meal", "cauldron", "infinite water", "diamond"]
Row_options=[Row1_options,Row2_options,Row3_options]

Row1_exceptions=["grass","mushroom","dirt","apple","glowstone"]
Row2_exceptions=["flint","glass"]
Row3_exceptions=["chest"]
Row_exceptions=[Row1_exceptions,Row2_exceptions,Row3_exceptions]
# "nothing" is a placeholder if there are less than 2 conditions required
nothing=0
# Row 1
Row1_clause1=[(0,0), (0,0), (0,0), (1,2), (1,9), (1,10), (1,11)]
Row1_clause1_amount=[1, 1, 30, 1, 1, 1, 1, 1]
Row1_clause2=[(0,1), (2,3), (nothing,nothing), (1,3), (2,9), (2,8), (0,5)]
Row1_clause2_amount=[1, 1, 0, 1, 1, 1, 1, 1]
# What to increase
Row1_incOrDec_var=[(0,2) ,(0,4), (0,6), (0,7), (0,9), (0,10), (0,11)]
Row1_incOrDec_amount=[1, 1, 2, 1, 1, 2, 1]

# Row 2
Row2_clause1=[(0,3), (1,0), (1,1), (1,2), (1,4), (1,4), (2,4), (2,6),(2,10), (2,11)]
Row2_clause1_amount=[1, 1, 1, 1, 8, 1, 1, 3, 1, 24]
Row2_clause2=[(0,1), (0,2), (0,3), (0,7), (nothing,nothing), (1,2), (0,6), (nothing,nothing), (0,8), (nothing,nothing)]
Row2_clause2_amount=[1, 1, 1, 1, 0, 1, 1, 0, 1, 0]

Row2_incOrDec_var=[(1,0), (1,1), (1,2), (1,4), (1,5), (1,6), (1,8), (1,9), (1,10), (1,11)]
Row2_incOrDec_amount=[1, 1, 2, 2, 1, 2, 1, 1, 1, 1]

# Row 3
Row3_clause1=[(2,0), (2,1), (2,1), (1,7), (1,3), (2,8), (2,6), (2,7), (2,6),(0,9), (0,10)]
Row3_clause1_amount=[1, 4, 2, 3, 1, 5, 1, 1, 5, 2, 1]
Row3_clause2=[(1,3), (nothing,nothing), (nothing,nothing), (nothing,nothing), (0,7), (nothing,nothing), (2,3), (nothing,nothing), (nothing,nothing), (1,9), (0,5)]
Row3_clause2_amount=[1, 0, 0, 0, 1, 0, 1, 0, 0, -2, 1]

Row3_incOrDec_var=[(2,1), (2,2), (2,3), (2,4), (2,5), (2,6), (2,7), (2,8), (2,9), (2,10), (2,11)]
Row3_incOrDec_amount=[1, 1, 4, 3, 2, 1, 1, 3, 1, 1, 1]

########################

Row_incOrDec_var=[Row1_incOrDec_var, Row2_incOrDec_var, Row3_incOrDec_var]
Row_incOrDec_amount=[Row1_incOrDec_amount, Row2_incOrDec_amount, Row3_incOrDec_amount]


Row_clause1=[Row1_clause1,Row2_clause1,Row3_clause1]
Row_clause2=[Row1_clause2,Row2_clause2,Row3_clause2]

Row_clause1_amount=[Row1_clause1_amount, Row2_clause1_amount, Row3_clause1_amount]
Row_clause2_amount=[Row1_clause2_amount, Row2_clause2_amount, Row3_clause2_amount]

###########################  Game  ####################

while game:
    last_turn=turns
    window.fill((255,255,255))
    for event in pygame.event.get():
        if event.type == pygame.KEYDOWN:
            x, y=pygame.mouse.get_pos()
            # Breaking stuff
            if event.key == pygame.K_RETURN:
                row1_check=[]
                row2_check=[]
                row3_check=[]
                while len(row1_check) != len(itemVariablesRow1):
                    row1_check.append(itemVariablesRow1[len(row1_check)])
                while len(row2_check) != len(itemVariablesRow2):
                    row2_check.append(itemVariablesRow2[len(row2_check)])
                while len(row3_check) != len(itemVariablesRow3):
                    row3_check.append(itemVariablesRow3[len(row3_check)])
                x, y=pygame.mouse.get_pos()
                # seeds
                if x >= 15 and x <= 115 and y <= 415 and y >= 315:
                    y_n=random.randint(1,3)
                    if y_n == 1:
                        itemVariablesRow1[0]+=1
                # mushroom
                if x >= 145 and x <= 245 and y <= 415 and y >= 315:
                    y_n=random.randint(1,12)
                    if y_n == 1 or y_n == 2:
                        itemVariablesRow1[1]+=random.randint(1,2)
                        y_n=random.randint(1,5)
                        if y_n == 1:
                            itemVariablesRow1[0]+=1
                    if y_n == 3:
                        itemVariablesRow1[0]+=1
                # podzol --> dirt
                if x >= 405 and x <= 535 and y <= 415 and y >= 315 and itemVariablesRow1[2] >= 1:
                    itemVariablesRow1[3]+=1
                    itemVariablesRow1[2]-=1
                # leaves --> apple
                if x >= 665 and x <= 795 and y <= 415 and y >= 315 and itemVariablesRow1[4] >= 1:
                    y_n=random.randint(1,8)
                    if y_n == 1:
                        itemVariablesRow1[5]+=1
                    else:
                        turns-=1
                    itemVariablesRow1[4]-=1
                # gravel --> flint
                if x >= 405 and x <= 535 and y <= 270 and y >= 170 and itemVariablesRow2[2] >= 1:
                    itemVariablesRow2[3]+=1
                    itemVariablesRow2[2]-=1
                # chest
                if x >= 15 and x <= 115 and y <= 155 and y >= 25:
                    y_n=random.randint(1,20)
                    if y_n == 1:
                        itemVariablesRow3[0]+=1
                # witch egg
                if x >= 1055 and x <= 1155 and y <= 270 and y >= 170 and itemVariablesRow2[8] >= 1:
                    loot=[(0,8), (2,4), redstone, gunpowder, "stick"]
                    number=random.randint(0,4)
                    if loot[number] == "stick":
                        itemVariablesRow3[3]+=random.randint(3,6)
                    elif loot[number] == redstone or loot[number] == gunpowder:
                        print(":|")
                    else:
                        itemVariablesRows[loot[number][0]][loot[number][1]]+=random.randint(1,4)
                    loot.remove(loot[number])
                    number=random.randint(0,3)
                    if loot[number] == "stick":
                        itemVariablesRow3[3]+=random.randint(3,6)
                    elif loot[number] == redstone or loot[number] == gunpowder:
                        print(":|")
                    else:
                        itemVariablesRows[loot[number][0]][loot[number][1]]+=random.randint(1,4)
                    loot.remove(loot[number])
                    itemVariablesRow2[8] -= 1
                if row1_check != itemVariablesRow1 or row2_check != itemVariablesRow2 or row3_check != itemVariablesRow3:
                    turns+=1
                # Filling A Water Bucket
                if x >= 1115 and x <= 1415 and y >= 25 and y <= 125 and itemVariablesRow2[9] >= 1 and itemVariablesRow3[10] >=1:
                    itemVariablesRow2[9]-=1
                    itemVariablesRow1[9]+=1
            
            # Smelting
            K_numbers=[pygame.K_1,pygame.K_2,pygame.K_3,pygame.K_4,pygame.K_5,pygame.K_6,pygame.K_7,pygame.K_8]
            numbers=[1,2,3,4,5,6,7,8]
            raw_row=[2,1]
            raw_num=[5,6]
            smelted_row=[2,1]
            smelted_num=[6,7]
            counter="no"
        # Iron
            if x >= 665 and x <= 765 and y <= 125 and y >= 25:
                counter=0
            elif x >= 795 and x <= 895 and y <= 285 and y >= 155:
                counter=1
            if counter != "no":
                if itemVariablesRows[raw_row[counter]][raw_num[counter]] >= 1 and itemVariablesRow1[7] >= 1 and itemVariablesRow2[5] >= 1:
                    raw_check=itemVariablesRows[raw_row[counter]][raw_num[counter]]
                    K_numbers=[pygame.K_1,pygame.K_2,pygame.K_3,pygame.K_4,pygame.K_5,pygame.K_6,pygame.K_7,pygame.K_8]
                    numbers=[1,2,3,4,5,6,7,8]
                    while len(numbers) != 0:
                        if event.key == K_numbers[numbers[0]-1]:
                            if itemVariablesRows[raw_row[counter]][raw_num[counter]] >= numbers[0]:
                                turns+=int(numbers[0]/2)
                                itemVariablesRows[raw_row[counter]][raw_num[counter]]-=numbers[0]
                                itemVariablesRows[smelted_row[counter]][smelted_num[counter]]+=numbers[0]
                                numbers=[0]
                        numbers.remove(numbers[0])
                    # if you smelted lose a coal
                    if raw_check != itemVariablesRows[raw_row[counter]][raw_num[counter]]:
                        itemVariablesRow1[7]-=1
                
            # Combining
            if event.key == pygame.K_SPACE:
                row=0
                while row != len(Row_clause1_amount):
                    counter=0
                    exception_counter=0
                    while counter != len(Row_options[row]):
                        if Row_options[row][counter] in Row_exceptions[row]:
                            counter+=1
                        else:
                            if x >= 15+(counter * 130) and x <= 145+(counter * 130) and y >= 315-(row * 145) and y <= 415-(row * 145):
                                if itemVariablesRows[Row_clause1[row][exception_counter][0]][Row_clause1[row][exception_counter][1]] >= Row_clause1_amount[row][exception_counter] and itemVariablesRows[Row_clause2[row][exception_counter][0]][Row_clause2[row][exception_counter][1]] >= Row_clause2_amount[row][exception_counter]:
                                    itemVariablesRows[Row_clause1[row][exception_counter][0]][Row_clause1[row][exception_counter][1]]-=Row_clause1_amount[row][exception_counter]
                                    itemVariablesRows[Row_clause2[row][exception_counter][0]][Row_clause2[row][exception_counter][1]]-=Row_clause2_amount[row][exception_counter]
                                    itemVariablesRows[Row_incOrDec_var[row][exception_counter][0]][Row_incOrDec_var[row][exception_counter][1]]+=Row_incOrDec_amount[row][exception_counter]
                                    turns+=1
                            counter+=1
                            exception_counter+=1
                    row+=1
    # Time
# Cauldron
    if itemVariablesRow3[9] >= 1 and cauldron_true == False:
        cauldron_true=True
        itemVariablesRow3[9]-=1
    if cauldron_true and int(turns/50) == turns/50 and itemVariablesRow3[9] < 1:
        itemVariablesRow3[9]+=1
        turns+=1
    if itemVariablesRow3[9] >= 1:
        pygame.draw.polygon(window, (40,85,255), ((1210,40), (1270,40), (1270, 55), (1210,55)))
    if cauldron_true:
        font.render_to(window,(1260,10), ": 1")
    #draw trophy
    ring_left=pygame.Rect(1455,335,40,20)
    ring_right=pygame.Rect(1495,335,40,20)
    main_cup=pygame.Rect(1470,300,50,80)
    block_top=pygame.Rect(1470,300,50,25)
    holder=pygame.Rect(1490,375,10,25)
    bottom=pygame.Rect(1470,395,50,10)
    pygame.draw.ellipse(window,(255,255,0),ring_left,5)
    pygame.draw.ellipse(window,(255,255,0),ring_right,5)
    pygame.draw.ellipse(window,(255,255,0),main_cup)
    pygame.draw.rect(window,(255,255,255),block_top)
    pygame.draw.rect(window,(255,255,0),holder)
    pygame.draw.ellipse(window,(255,255,0),bottom)
    
    #drawing the boxes
    counter=0
    while counter < 12:
        standard_box = pygame.Rect(15+counter*130,25,100,100)
        pygame.draw.rect(window, (0,0,0),standard_box, 3)
        standard_box.y+=145
        pygame.draw.rect(window, (0,0,0),standard_box, 3)
        standard_box.y+=145
        pygame.draw.rect(window, (0,0,0),standard_box, 3)
        #seperating lines
        pygame.draw.line(window, (0,0,0), (0,counter*145+145),(1560,counter*145+125+45/2),2)
        counter+=1
    # middle line
    pygame.draw.line(window,(0,0,0),(520,0),(520,440),5)
    pygame.draw.line(window,(0,0,0),(1040,0),(1040,440),5)
    # Titles and amounts
    counter=1
    row=0
    while row != 4:
        bold.render_to(window,(xOffsetRows[row-1][counter-1]+(counter*130),445-((row)*145)), itemTitlesRows[row-1][counter-1])
        font.render_to(window,(-115+(counter*130),565-(row*145)), itemNamesRows[row-1][counter-1] +": " +str(itemVariablesRows[row-1][counter-1]))
        if counter != 12:
            counter+=1
        else:
            row+=1
            counter=1
    # Row 1
    # Grass
    pygame.draw.line(window,(67, 132, 29), (25,405),(105,405), 5)
    counter=0
    while counter != 8:
        pygame.draw.line(window,(67, 132, 29),(30+counter*10,405),(30+counter*10,405-grass[counter]),5)
        counter+=1
    # Drawing
    row=0
    while row < len(Row_rects):
        counter=0
        while counter < len(Row_rects[row]):
            # Bucket
            if Row_rects[row][counter] == bucket_1 or Row_rects[row][counter] == bucket_2:
                pygame.draw.polygon(window, Row_colors[row][counter],Row_rects[row][counter],10)
            # Glass
            elif Row_rects[row][counter] == glass_rim:
                pygame.draw.rect(window, Row_colors[row][counter],Row_rects[row][counter],5)
            elif Row_rects[row][counter] == bottle:
                pygame.draw.polygon(window, Row_colors[row][counter],Row_rects[row][counter],5)
            elif Row_rects[row][counter] in ellipses:
                pygame.draw.ellipse(window, Row_colors[row][counter],Row_rects[row][counter])
            elif Row_rects[row][counter] in polygons:
                pygame.draw.polygon(window, Row_colors[row][counter],Row_rects[row][counter])
            else:
                pygame.draw.rect(window, Row_colors[row][counter],Row_rects[row][counter])
            counter+=1
        row+=1
    # Wood Planks
    pygame.draw.line(window, (0,0,0), (155,45),(235,45),3)
    pygame.draw.line(window, (0,0,0), (155,65),(235,65),3)
    pygame.draw.line(window, (0,0,0), (155,85),(235,85),3)
    pygame.draw.line(window, (0,0,0), (155,105),(235,105),3)
    # Crafting Table
    pygame.draw.line(window, (0,0,0), (285,35+int(80/3)),(365,35+int(80/3)),3)
    pygame.draw.line(window, (0,0,0), (285,35+int(80/3*2)),(365,35+int(80/3*2)),3)
    pygame.draw.line(window, (0,0,0), (285+int(80/3),35),(285+int(80/3),115),3)
    pygame.draw.line(window, (0,0,0), (285+int(80/3*2),35),(285+int(80/3*2),115),3)
    # Iron Ore
    counter=0
    while counter != 28:
        ore=pygame.Rect(iron[counter],iron[counter+1],10,10)
        pygame.draw.rect(window, (225,210,150),ore)
        counter+=2
    if turns != last_turn:
        print(turns)
    pygame.display.flip()
