## Welcome to my GitHub Pages

Hello. Thank you for visting my Github pages. You've come to the right place to download some of the Python projects that I've been working on. I would like to hear from you so please, feel free to send me a message to let me know what you think of my projects.
Any feedback is appreciated.

  ![MyPy](Screenshot-MyPy_Dodge.png) [GitHub/MyPy_Dodge](https://github.com/corro69/MyPy)  ![Spaced_Invaders](Screenshot-Spaced_Invaders.png) [GitHub/Spaced_Invaders](https://github.com/corro69/Spaced_invaders)

```markdown
import pygame

def game_loop():
    import Mainshmp

pygame.init()


display_width = 800
display_height = 800

HW,HH = display_width / 2, display_height / 2
AREA = display_width * display_height

white = (255,255,255)
black = (0,0,0,)
red = (255,0,0)
green = (0,255,0)
blue = (0,0,255)

player_width = 50
player_heigth = 50

gameDisplay = pygame.display.set_mode((display_width,display_height))
pygame.display.set_caption("MyPy")
icon = pygame.image.load("icon.png")
pygame.display.set_icon(icon)
clock = pygame.time.Clock()
pygame.font.init()

pygame.mixer.music.load("random silly chip song.wav")
pygame.mixer.music.play(-1)

class Background(pygame.sprite.Sprite):
    def __init__(self, image_file, location):
        pygame.sprite.Sprite.__init__(self)  #call Sprite initializer
        self.image = pygame.image.load("back.png")
        self.rect = self.image.get_rect()
        self.rect.left, self.rect.top = location
bg = Background('background_image.png', [0,0])
kenny = pygame.image.load("kenny.png")

button1 = pygame.image.load("button1.png")
button2 = pygame.image.load("button2.png")
quit1 = pygame.image.load("quit1.png")
quit2 = pygame.image.load("quit2.png")

def text_objects(text, font):
    textSurface = font.render(text, True, red)
    return textSurface, textSurface.get_rect()

def button(x,y,w,h, b1, b2, action=None):
    mouse = pygame.mouse.get_pos()
    click = pygame.mouse.get_pressed()

    gameDisplay.blit(b2,(x,y))
    if x + w > mouse[0] > x and y + h > mouse[1] > y:
        if click[0] == 1 and action != None:
            if action == "play":
                game_loop()
            elif action == "quit":
                pygame.quit()

        gameDisplay.blit(b1,(x,y))

def game_intro():
    intro = True

    while intro:

        for event in pygame.event.get():
            print(event)
            
            if event.type == pygame.QUIT:
                pygame.quit()
                quit()

            if event.type ==pygame.KEYDOWN:
                if event.key == pygame.K_ESCAPE:
                    pygame.quit()
                    quit()
            
            if event.type ==pygame.KEYDOWN:
                if event.key == pygame.K_p:
                    game_loop()

        gameDisplay.blit(bg.image, bg.rect)

        gameDisplay.blit(kenny,(350, 350))

        largeText = pygame.font.Font('SnackerComic.ttf',115)
        TextSurf, TextRect = text_objects("MyPy", largeText)
        TextRect.center = ((display_width/2),(display_height/3))
        gameDisplay.blit(TextSurf, TextRect)

        button(200,500,100,39,button1,button2, "play")
        button(500,500,100,39,quit1,quit2, "quit")
	
        pygame.display.update()
        clock.tick(15)

game_intro()
pygame.quit()
quit
```

### Support or Contact
<dustin.brooks@massconceptz.com>
<dbrooks@linuxmail.org>
