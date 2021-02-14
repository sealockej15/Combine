import pygame, random
pygame.init()
def set_up():
    #draw grass
    pygame.draw.line(w,grass_color,(10,465),(10,410),5)
    pygame.draw.line(w,grass_color,(17,465),(17,403),5)
    pygame.draw.line(w,grass_color,(24,465),(24,386),5)
    pygame.draw.line(w,grass_color,(31,465),(31,405),5)
    pygame.draw.line(w,grass_color,(38,465),(38,408),5)
    pygame.draw.line(w,grass_color,(45,465),(45,423),5)
    pygame.draw.line(w,grass_color,(52,465),(52,396),5)
    pygame.draw.line(w,grass_color,(59,465),(59,403),5)
    pygame.draw.line(w,grass_color,(66,465),(66,380),5)
    pygame.draw.line(w,grass_color,(73,465),(73,414),5)
    pygame.draw.line(w,grass_color,(82,465),(82,406),5)
    pygame.draw.line(w,grass_color,(90,465),(90,384),5)
    pygame.draw.line(w,grass_color,(10,466),(90,466),3)
    # seperaters
    pygame.draw.line(w,(0,0,0),(550,0),(550,660),5)
    pygame.draw.line(w,(0,0,0),(0,475),(1160,475))
    pygame.draw.line(w,(0,0,0),(0,630),(1050,630))
    pygame.draw.line(w,(0,0,0),(0,500),(1160,500))
    pygame.draw.line(w,(0,0,0),(0,335),(1160,335))
    pygame.draw.line(w,(0,0,0),(0,310),(1160,310))
    pygame.draw.line(w,(0,0,0),(0,170),(1160,170))
    pygame.draw.line(w,(0,0,0),(0,140),(1160,140))
    #boxes
    pygame.draw.rect(w,(0,0,0),bone_box,5)
    pygame.draw.rect(w,(0,0,0),nugget_box,5)
    pygame.draw.rect(w,(0,0,0),bottle_box,5)
    pygame.draw.rect(w,(0,0,0),glass_box,5)
    pygame.draw.rect(w,(0,0,0),sand_box,5)
    pygame.draw.rect(w,(0,0,0),furnace_box,5)
    pygame.draw.rect(w,(0,0,0),cobble_box,5)
    pygame.draw.rect(w,(0,0,0),coal_box,5)
    pygame.draw.rect(w,(0,0,0),egg_box,5)
    pygame.draw.rect(w,(0,0,0),apple_box,5)
    pygame.draw.rect(w,(0,0,0),leaf_box,5)
    pygame.draw.rect(w,(0,0,0),stick_box,5)
    pygame.draw.rect(w,(0,0,0),crafting_table_box,5)
    pygame.draw.rect(w,(0,0,0),wood_plank_box,5)
    pygame.draw.rect(w,(0,0,0),chest_box,5)
    pygame.draw.rect(w,(0,0,0),mushroom_box,5)
    pygame.draw.rect(w,(0,0,0),podzol_box,5)
    pygame.draw.rect(w,(0,0,0),dirt_box,5)
    pygame.draw.rect(w,(0,0,0),seed_box,5)
    pygame.draw.rect(w,(0,0,0),mycelium_box,5)
    pygame.draw.rect(w,(0,0,0),coarse_box,5)
    pygame.draw.rect(w,(0,0,0),gravel_box,5)
    pygame.draw.rect(w,(0,0,0),flint_box,5)
    pygame.draw.rect(w,(0,0,0),iron_box,5)
    pygame.draw.rect(w,(0,0,0),ingot_box,5)
    pygame.draw.rect(w,(0,0,0),sugar_box,5)
    pygame.draw.rect(w,(0,0,0),redstone_box,5)
    pygame.draw.rect(w,(0,0,0),glowstone_box,5)
    #say names
    say_dirt = myfont.render("dirt", False, (0, 0, 0))
    w.blit(say_dirt,(425,335))
    say_podzol = myfont.render("podzol", False, (0, 0, 0))
    w.blit(say_podzol,(290,335))
    say_grass = myfont.render("grass", False, (0, 0, 0))
    w.blit(say_grass,(2.5,335))
    say_mushroom = myfont.render("mushroom block", False, (0, 0, 0))
    w.blit(say_mushroom,(122.5,335))
    say_mycelium = myfont.render("mycelium", False, (0, 0, 0))
    w.blit(say_mycelium,(0,170))
    say_coarse = myfont.render("coarse dirt", False, (0, 0, 0))
    w.blit(say_coarse,(140,170))
    say_gravel = myfont.render("gravel", False, (0, 0, 0))
    w.blit(say_gravel,(300,170))
    say_flint = myfont.render("flint", False, (0, 0, 0))
    w.blit(say_flint,(410,170))
    say_chest = myfont.render("chest", False, (0, 0, 0))
    w.blit(say_chest,(0,10))
    say_chest = myfont.render("wood plank", False, (0, 0, 0))
    w.blit(say_chest,(125,10))
    say_crafting_table  = myfont.render("crafting table", False, (0, 0, 0))
    w.blit(say_crafting_table,(280,10))
    say_stick  = myfont.render("stick", False, (0, 0, 0))
    w.blit(say_stick,(450,10))
    say_leaf  = myfont.render("leaf", False, (0, 0, 0))
    w.blit(say_leaf,(555,335))
    say_apple  = myfont.render("apple", False, (0, 0, 0))
    w.blit(say_apple,(680,335))
    say_egg  = myfont.render("egg", False, (0, 0, 0))
    w.blit(say_egg,(800,335))
    say_coal  = myfont.render("coal", False, (0, 0, 0))
    w.blit(say_coal,(925,335))
    say_cobble  = myfont.render("cobble stone", False, (0, 0, 0))
    w.blit(say_cobble,(555,175))
    say_furnace  = myfont.render("furnace", False, (0, 0, 0))
    w.blit(say_furnace,(695,175))
    say_sand  = myfont.render("sand", False, (0, 0, 0))
    w.blit(say_sand,(820,175))
    say_glass  = myfont.render("glass", False, (0, 0, 0))
    w.blit(say_glass,(945,175))
    say_bottle  = myfont.render("bottle", False, (0, 0, 0))
    w.blit(say_bottle,(555,5))
    say_iron  = myfont.render("iron ore", False, (0, 0, 0))
    w.blit(say_iron,(680,5))
    say_ingot  = myfont.render("iron ingot", False, (0, 0, 0))
    w.blit(say_ingot,(805,5))
    say_nugget  = myfont.render("iron nugget", False, (0, 0, 0))
    w.blit(say_nugget,(930,5))
    say_bone  = myfont.render("bone", False, (0, 0, 0))
    w.blit(say_bone,(5,502.5))
    say_sugar = myfont.render("sugar", False, (0, 0, 0))
    w.blit(say_sugar,(1060,5))
    say_glowstone = myfont.render("glow stone", False, (0, 0, 0))
    w.blit(say_glowstone,(1060,345))
    say_redstone = myfont.render("red stone", False, (0, 0, 0))
    w.blit(say_redstone,(1060,180))
    #draw blocks
    pygame.draw.line(w,(56, 44, 13),(500,50),(500,130),20)
    pygame.draw.polygon(w,(0,0,0),((490,215),(490,295),(420,295)))
    pygame.draw.rect(w,(124, 106, 58),wood_plank_block)
    space=20
    pygame.draw.line(w,(0,0,0),(135,40+space),(213,40+space),3)
    space+=20
    pygame.draw.line(w,(0,0,0),(135,40+space),(213,40+space),3)
    space+=20
    pygame.draw.line(w,(0,0,0),(135,40+space),(213,40+space),3)
    space+=20
    pygame.draw.line(w,(0,0,0),(135,40+space),(213,40+space),3)
    space+=20
    pygame.draw.circle(w,(216, 215, 164),(850,420),40)
    pygame.draw.circle(w,(255,0,0),(725,420),40)
    pygame.draw.rect(w,(73, 54, 2),crafting_table_block)
    pygame.draw.line(w,(56, 42, 5),(290,76.6),(369,76.6),3)
    pygame.draw.line(w,(56, 42, 5),(290,103.2),(369,103.2),3)
    pygame.draw.line(w,(56, 42, 5),(316.6,50),(316.6,129),3)
    pygame.draw.line(w,(56, 42, 5),(343.2,50),(343.2,129),3)
    pygame.draw.rect(w,(28, 132, 18),leaf_block)
    pygame.draw.rect(w,(193, 165, 133),mushroom_block)
    pygame.draw.rect(w,(104, 83, 59),podzol_dirt)
    pygame.draw.rect(w,(94, 53, 7),podzol_top)
    pygame.draw.rect(w,(104, 83, 59),dirt_block)
    pygame.draw.rect(w,(104, 83, 59),mycelium_dirt)
    pygame.draw.rect(w,(120, 113, 130),mycelium_top)
    pygame.draw.rect(w,(79, 57, 3),coarse_dirt)
    pygame.draw.rect(w,(125,128,132),gravel_block)
    pygame.draw.rect(w,(107, 83, 22),chest_block)
    pygame.draw.rect(w,(94, 97, 99),cobble_block)
    pygame.draw.rect(w,(68, 68, 68),furnace_block)
    pygame.draw.rect(w,(255,255,0),sand_block)
    pygame.draw.rect(w,(215, 227, 247),glass_block,5)
    pygame.draw.rect(w,(239, 243, 249),glass_block)
    pygame.draw.rect(w,(105, 109, 105),iron_block)
    pygame.draw.polygon(w,(211,211,211),((970,75),(990,75),(990,95),(970,95)))
    pygame.draw.polygon(w,(238, 234, 217),((15,570),(95,570),(95,590),(15,590)))
    pygame.draw.polygon(w,(211,211,211),((815,65),(895,65),(895,105),(815,105)))
    pygame.draw.polygon(w,(255, 110, 0),((710,255),(750,255),(750,275),(710,275)))
    pygame.draw.polygon(w,(0, 0, 0),((710,255),(750,255),(750,275),(710,275)),3)
    pygame.draw.line(w,(0,0,0),(10,80),(89,80),10)
    pygame.draw.polygon(w,(255,255,255),((40,70),(60,70),(60,100),(40,100)))
    pygame.draw.polygon(w,(0,0,0),((40,70),(60,70),(60,100),(40,100)),5)
    pygame.draw.polygon(w,(0,0,0),((935,460),(1015,460),(975,380)))
    pygame.draw.polygon(w,(170, 145, 107),((585,45),(625,45),(625,75),(585,75)))
    pygame.draw.polygon(w,(215, 227, 247),((585,45),(625,45),(625,75),(635,75),(635,125),(575,125),(575,75),(585,75)),5)
    pygame.draw.polygon(w,(0,0,0),((40,70),(60,70),(60,100),(40,100)),5)
    pygame.draw.polygon(w,(255,255,0),((1070,460),(1110,380),(1150,460)))
    pygame.draw.polygon(w,(0,0,0),((1070,460),(1110,380),(1150,460)),5)
    pygame.draw.polygon(w,(0,0,0),((1070,295),(1110,215),(1150,295)),5)
    pygame.draw.polygon(w,(255,0,0),((1070,295),(1110,215),(1150,295)))
    pygame.draw.polygon(w,(0,0,0),((1070,120),(1110,40),(1150,120)),5)
    #start check
    if meal_start:
        say_meal  = myfont.render("bone meal", False, (0, 0, 0))
        w.blit(say_meal,(130,502.5))
        pygame.draw.rect(w,(0,0,0),meal_box,5)
        meal_draw = myfont.render(meal, False, (0, 0, 0))
        w.blit(meal_draw,(130,632.5))
        pygame.draw.polygon(w,(222, 227, 234),((160,560),(200,560),(200,600),(160,600)))
    if witch_start:
        pygame.draw.rect(w,(0,0,0),witch_box,5)
        say_question  = myfont.render("?????????", False, (0, 0, 0))
        w.blit(say_question,(255,502.5))
        question_draw = myfont.render(question, False, (0, 0, 0))
        w.blit(question_draw,(255,632.5))
        pygame.draw.circle(w,(0,0,0),(305,580),40,5)
        pygame.draw.polygon(w,(0,0,0),((290,572.5),(290,552.5),(320,552.5),(320,587.5),(320,552.5),(290,552.5)),5)
        pygame.draw.polygon(w,(0,0,0),((320,597.5),(322.5,597.5),(322.5,600),(320,600)),5)
#set up
w=pygame.display.set_mode([550,500])
w.fill((255,255,255))
myfont = pygame.font.SysFont('arial', 25)
#variables
    #starts
mystery_drops=False
meal_start=False
witch_start=True
    #metal
iron_amount=0
ingot_amount=1
nugget_amount=0
    #dirt
podzol_amount=0
dirt_amount=0
coarse_amount=0
mycelium_amount=0
    #infinity
chest_amount=0
mushroom_amount=0
seed_amount=0
    #wood
wood_plank_amount=4
crafting_table_amount=0
stick_amount=0
    #misc
glass_amount=0
furnace_amount=0
cobble_amount=0
gravel_amount=0
flint_amount=0
leaf_amount=0
coal_amount=0
sand_amount=0
bone_amount=0
    #diamond related
bottle_amount=1
apple_amount=0
egg_amount=1
meal_amount=0
witch_amount=0
drops_amount=0
redstone_amount=0
glowstone_amount=0
sugar_amount=0
rotten_flesh_amount=0
lapis_amount=0
dye_amount=0
diamond_amount=0
#colors
grass_color=(67, 132, 29)
pygame.display.flip()
running=True
#rects
sugar_box=pygame.Rect(1060,370,100,100)
glowstone_box=pygame.Rect(1060,205,100,100)
redstone_box=pygame.Rect(1060,30,100,100)
witch_box=pygame.Rect(255,530,100,100)
meal_box=pygame.Rect(130,530,100,100)
bone_box=pygame.Rect(5,530,100,100)
nugget_box=pygame.Rect(930,35,100,100)
ingot_box=pygame.Rect(805,35,100,100)
iron_block=pygame.Rect(690,45,80,80)
iron_box=pygame.Rect(680,35,100,100)
bottle_box=pygame.Rect(555,35,100,100)
glass_block=pygame.Rect(940,215,80,80)
glass_box=pygame.Rect(930,205,100,100)
sand_block=pygame.Rect(815,215,80,80)
sand_box=pygame.Rect(805,205,100,100)
furnace_block=pygame.Rect(690,215,80,80)
furnace_box=pygame.Rect(680,205,100,100)
cobble_block=pygame.Rect(565,215,80,80)
cobble_box=pygame.Rect(555,205,100,100)
coal_box=pygame.Rect(925,370,100,100)
egg_box=pygame.Rect(800,370,100,100)
apple_box=pygame.Rect(675,370,100,100)
leaf_block=pygame.Rect(560,380,80,80)
leaf_box=pygame.Rect(550,370,100,100)
stick_box=pygame.Rect(450,40,100,100)
crafting_table_block=pygame.Rect(290,50,80,80)
crafting_table_box=pygame.Rect(280,40,100,100)
wood_plank_block=pygame.Rect(135,50,80,80)
wood_plank_box=pygame.Rect(125,40,100,100)
chest_block=pygame.Rect(10,50,80,80)
chest_box=pygame.Rect(0,40,100,100)
flint_box=pygame.Rect(410,205,100,100)
gravel_block=pygame.Rect(295,215,80,80)
gravel_box=pygame.Rect(285,205,100,100)
coarse_dirt=pygame.Rect(150,215,80,80)
coarse_box=pygame.Rect(140,205,100,100)
mycelium_top=pygame.Rect(10,215,80,20)
mycelium_box=pygame.Rect(0,205,100,100)
mycelium_dirt=pygame.Rect(10,215,80,80)
dirt_block=pygame.Rect(435,382.5,80,80)
dirt_box=pygame.Rect(425,372.5,100,100)
podzol_top=pygame.Rect(285,382.5,80,20)
podzol_dirt=pygame.Rect(285,382.5,80,80)
podzol_box=pygame.Rect(275,372.5,100,100)
mushroom_box=pygame.Rect(125,372.5,100,100)
mushroom_block=pygame.Rect(135,382.5,80,80)
seed_box=pygame.Rect(0,372.5,100,100)
#main loop
while running:
    # event loop
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running=False
        if event.type == pygame.MOUSEBUTTONDOWN:
            x,y=pygame.mouse.get_pos()
            #check if you get item
            if x >= 0 and x <= 100 and y >= 372.5 and y <= 475:
                yes_or_no=random.randint(1,8)
                if yes_or_no == 1:
                    seed_amount+=1
            if x >= 125 and x <= 225 and y >= 372.5 and y <= 475:
                yes_or_no=random.randint(1,8)
                if yes_or_no == 1:
                    mushroom_plus=random.randint(0,2)
                    mushroom_amount+=mushroom_plus
            if x >= 425 and x <= 525 and y >= 372.5 and y <= 475:
                if podzol_amount >= 1:
                    dirt_amount+=1
                    podzol_amount-=1
            if x >= 410 and x <= 510 and y >= 205 and y <= 305:
                if gravel_amount >= 1:
                    flint_amount+=1
                    gravel_amount-=1
            if x >= 0 and x <= 100 and y >= 40 and y <= 140:
                yes_or_no=random.randint(1,50)
                if yes_or_no == 1:
                    chest_amount+=1
            if x >= 675 and x <= 775 and y >= 370 and y <= 470:
                if leaf_amount >= 1:
                    leaf_amount-=1
                    yes_or_no=random.randint(1,8)
                    if yes_or_no == 1:
                        apple_amount+=1
            if x >= 255 and x <= 355 and y >= 530 and y <= 630:
                if witch_amount >= 1:
                    a=1
                    drops=["redstone","glowstone","sugar","stick","bottle"]
                    while a <= 2:
                        drop_rand=random.randint(0,len(drops)-1)
                        drop=drops[drop_rand]
                        drops.remove(drop)
                        if drop == "redstone":
                            redstone_amount+=random.randint(0,6)
                        elif drop == "glowstone":
                            glowstone_amount+=random.randint(0,6)
                        elif drop == "stick":
                            stick_amount+=random.randint(0,6)
                        elif drop == "sugar":
                            sugar_amount+=random.randint(0,6)
                        elif drop == "bottle":
                            bottle_amount+=random.randint(0,6)
                        a+=1
                    witch_amount-=1
                    rotten_flesh=True
        if event.type == pygame.KEYDOWN:
            if event.key == pygame.K_SPACE:
                x,y=pygame.mouse.get_pos()
                if x >= 450 and x <= 550 and y >= 40 and y <= 140:
                    if wood_plank_amount >= 2:
                        wood_plank_amount-=2
                        stick_amount+=4
                if x >= 275 and x <= 375 and y >= 372.5 and y <= 475:
                    if seed_amount >= 1 and mushroom_amount >= 1:
                        seed_amount-=1
                        mushroom_amount-=1
                        podzol_amount+=1
                if x >= 290 and x <= 390 and y >= 40 and y <= 140:
                    if wood_plank_amount >= 4:
                        wood_plank_amount-=4
                        crafting_table_amount+=1
                        w=pygame.display.set_mode((1050,500))
                if x >= 0 and x <= 100 and y >= 205 and y <= 305:
                    if mushroom_amount >= 1 and dirt_amount >= 1:
                        dirt_amount-=1
                        mushroom_amount-=1
                        mycelium_amount+=1
                if x >= 140 and x <= 240 and y >= 205 and y <= 305:
                    if mycelium_amount >= 1 and podzol_amount >= 1:
                        podzol_amount-=1
                        mycelium_amount-=1
                        coarse_amount+=1
                if x >= 285 and x <= 385 and y >= 205 and y <= 305:
                    if coarse_amount >= 1 and dirt_amount >= 1:
                        coarse_amount-=1
                        dirt_amount-=1
                        gravel_amount+=2
                if x >= 125 and x <= 225 and y >= 40 and y <= 140:
                    if flint_amount >= 1 and chest_amount >= 1:
                        flint_amount-=1
                        chest_amount-=1
                        wood_plank_amount+=1
                if x >= 550 and x <= 650 and y >= 370 and y <= 470:
                    if seed_amount >= 1 and stick_amount >= 1:
                        seed_amount-=1
                        stick_amount-=1
                        leaf_amount+=1
                if x >= 800 and x <= 900 and y >= 370 and y <= 470:
                    if seed_amount >= 30:
                        seed_amount-=30
                        egg_amount+=1
                if x >= 925 and x <= 1025 and y >= 370 and y <= 470:
                    if gravel_amount >= 1 and flint_amount >= 1:
                        gravel_amount-=1
                        flint_amount-=1
                        coal_amount+=1
                if x >= 555 and x <= 655 and y >= 205 and y <= 305:
                    if gravel_amount >= 1 and coal_amount >= 1:
                        coal_amount-=1
                        gravel_amount-=1
                        cobble_amount+=2
                if x >= 680 and x <= 780 and y >= 205 and y <= 305:
                    if cobble_amount >= 8:
                        cobble_amount-=8
                        furnace_amount+=1
                if x >= 815 and x <= 915 and y >= 205 and y <= 305:
                    if gravel_amount >= 1 and cobble_amount >= 1:
                        cobble_amount-=1
                        gravel_amount-=1
                        sand_amount+=1
                if x >= 930 and x <= 1030 and y >= 205 and y <= 305:
                    if sand_amount >= 3 and coal_amount >= 1 and furnace_amount >= 1:
                        sand_amount-=3
                        coal_amount-=1
                        glass_amount+=3
                if x >= 555 and x <= 655 and y >= 35 and y <= 135:
                    if glass_amount >= 3:
                        glass_amount-=3
                        bottle_amount+=3
                if x >= 680 and x <= 780 and y >= 35 and y <= 135:
                    if flint_amount >= 1 and coal_amount >= 1:
                        coal_amount-=1
                        flint_amount-=1
                        iron_amount+=1
                if x >= 805 and x <= 905 and y >= 35 and y <= 135:
                    if iron_amount >= 1 and coal_amount >= 1 and furnace_amount >= 1:
                        coal_amount-=1
                        iron_amount-=1
                        ingot_amount+=1
                if x >= 930 and x <= 1030 and y >= 35 and y <= 135:
                    if ingot_amount >= 1:
                        ingot_amount-=1
                        nugget_amount+=9
                        w=pygame.display.set_mode([1160,660])
                if x >= 5 and x <= 105 and y >= 530 and y <= 630:
                    if nugget_amount >= 1 and stick_amount >= 1:
                        nugget_amount-=1
                        stick_amount-=1
                        bone_amount+=1
                        meal_start=True
                if x >= 130 and x <= 230 and y >= 530 and y <= 630:
                    if bone_amount >= 1 and meal_start:
                        bone_amount-=1
                        meal_amount+=3
                        witch_start=True
                if x >= 255 and x <= 355 and y >= 530 and y <= 630:
                    if bottle_amount >= 1 and witch_start and egg_amount >= 1:
                        egg_amount-=1
                        bottle_amount-=1
                        witch_amount+=1
                        mystery_drops=True
    #printing out how much
    mushroom="mushrooms: " +str(mushroom_amount)
    seed="seeds: " +str(seed_amount)
    podzol="podzol: " +str(podzol_amount)
    dirt="dirt: " +str(dirt_amount)
    mycelium="mycelium: " +str(mycelium_amount)
    coarse="coarse dirt: " +str(coarse_amount)
    gravel="gravel: " +str(gravel_amount)
    flint="flint: " +str(flint_amount)
    chest="chests: " +str(chest_amount)
    wood_plank="wood planks: " +str(wood_plank_amount)
    crafting_table="crafting tables: " +str(crafting_table_amount)
    stick="sticks: " +str(stick_amount)
    leaf="leafs: " +str(leaf_amount)
    apple="apples: " +str(apple_amount)
    egg="eggs: " +str(egg_amount)
    coal="coal: " +str(coal_amount)
    cobble="cobble: " +str(cobble_amount)
    furnace="furnaces: " +str(furnace_amount)
    sand="sand: " +str(sand_amount)
    glass="glass: " +str(glass_amount)
    bottle="bottles: " +str(bottle_amount)
    iron="irons: " +str(iron_amount)
    ingot="ingots: " +str(ingot_amount)
    nugget="nuggets: " +str(nugget_amount)
    bone="bones: " +str(bone_amount)
    meal="meals: " +str(meal_amount)
    question="???s: " +str(witch_amount)
    redstone="redstone: " +str(redstone_amount)
    glowstone="glowstone: " +str(glowstone_amount)
    sugar="sugar: " +str(sugar_amount)
    w.fill((255,255,255))
    set_up()
    seed_draw = myfont.render(seed, False, (0, 0, 0))
    podzol_draw = myfont.render(podzol, False, (0, 0, 0))
    mushroom_draw = myfont.render(mushroom, False, (0, 0, 0))
    dirt_draw = myfont.render(dirt, False, (0, 0, 0))
    mycelium_draw = myfont.render(mycelium, False, (0, 0, 0))
    coarse_draw = myfont.render(coarse, False, (0, 0, 0))
    gravel_draw = myfont.render(gravel, False, (0, 0, 0))
    flint_draw = myfont.render(flint, False, (0, 0, 0))
    chest_draw = myfont.render(chest, False, (0, 0, 0))
    wood_plank_draw = myfont.render(wood_plank, False, (0, 0, 0))
    crafting_table_draw = myfont.render(crafting_table, False, (0, 0, 0))
    stick_draw = myfont.render(stick, False, (0, 0, 0))
    leaf_draw = myfont.render(leaf, False, (0, 0, 0))
    apple_draw = myfont.render(apple, False, (0, 0, 0))
    egg_draw = myfont.render(egg, False, (0, 0, 0))
    coal_draw = myfont.render(coal, False, (0, 0, 0))
    cobble_draw = myfont.render(cobble, False, (0, 0, 0))
    furnace_draw = myfont.render(furnace, False, (0, 0, 0))
    sand_draw = myfont.render(sand, False, (0, 0, 0))
    glass_draw = myfont.render(glass, False, (0, 0, 0))
    bottle_draw = myfont.render(bottle, False, (0, 0, 0))
    iron_draw = myfont.render(iron, False, (0, 0, 0))
    ingot_draw = myfont.render(ingot, False, (0, 0, 0))
    nugget_draw = myfont.render(nugget, False, (0, 0, 0))
    bone_draw = myfont.render(bone, False, (0, 0, 0))
    glowstone_draw = myfont.render(glowstone, False, (0, 0, 0))
    redstone_draw = myfont.render(redstone, False, (0, 0, 0))
    sugar_draw = myfont.render(sugar, False, (0, 0, 0))
    w.blit(sugar_draw,(1060,140))
    w.blit(redstone_draw,(1025,310))
    w.blit(glowstone_draw,(1025,470))
    w.blit(bone_draw,(5,632.5))
    w.blit(nugget_draw,(930,135))
    w.blit(ingot_draw,(805,135))
    w.blit(iron_draw,(680,135))
    w.blit(bottle_draw,(555,135))
    w.blit(glass_draw,(930,305))
    w.blit(sand_draw,(805,305))
    w.blit(furnace_draw,(680,305))
    w.blit(cobble_draw,(555,305))
    w.blit(coal_draw,(925,475))
    w.blit(egg_draw,(800,475))
    w.blit(apple_draw,(675,475))
    w.blit(leaf_draw,(555,475))
    w.blit(stick_draw,(450,145))
    w.blit(crafting_table_draw,(280,145))
    w.blit(wood_plank_draw,(120,145))
    w.blit(chest_draw,(0,145))
    w.blit(flint_draw,(410,310))
    w.blit(gravel_draw,(285,310))
    w.blit(coarse_draw,(140,310))
    w.blit(mycelium_draw,(0,310))
    w.blit(mushroom_draw,(125,475))
    w.blit(podzol_draw,(285,475))
    w.blit(dirt_draw,(425,475))
    w.blit(seed_draw,(0,475))
    pygame.display.flip()
