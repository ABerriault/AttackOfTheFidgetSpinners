// Venture 2017
// Gr 6-8 Coding Workshop
// Attack of the Fidget Spinners
 
Player p = new Player(200, 550, 25, 25, 10);
PImage img;
String url = "https://www.spigotmc.org/data/resource_icons/41/41184.jpg?1495413880";
ArrayList <Enemy> spinners = new ArrayList<Enemy>();
ArrayList <Projectile> shots = new ArrayList <Projectile>();
 
int level = 0;
int lives = 3;
int EnemyTimer = 0;
 
void setup() {
  size(600, 600);
  imageMode(CENTER);
  img = loadImage(url, "png");
  //img = loadImage("spinner.jpg");
 
  fill(230);
  textAlign(CENTER, CENTER);
  textSize(32);
}
 
void draw() {
  background(0);
  p.draw();
  if (lives > 0) {
    fill(230);
    text("Lives: "+lives, 0, 0, 150, 50 );
    text("Score: "+level, 450, 0, 150, 50 );
    displayEnemies();
    displayShots();
    checkCollisions();
  } else {
    text("Game Over", 0, 0, 600, 600 );
    text("Score: "+level, 0, 100, 600, 500);
  }
}
 
void keyPressed() {
  if (key == 'a') {
    p.moveLeft();
  } else if (key == 'd') {
    p.moveRight();
  } else if (key == ' ') {
    shots.add(p.shoot());
  }
}
 
void displayEnemies() {
  if (EnemyTimer == 120 - 1 * level) {
    spinners.add(new Enemy(int(random(25, 575)), 0, 50, 50, 1, img));
    EnemyTimer = 0;
    level++;
  }
  if (spinners.size()>0) {
    for (Enemy i : spinners) {
      i.draw();
    }
  }
  EnemyTimer++;
}
 
void displayShots() {
  for (Projectile p : shots) {
    p.draw();
  }
}
 
void checkCollisions() {
  for (int j = spinners.size() - 1; j >= 0; j--) {
    Enemy e = spinners.get(j);
    for (int i = shots.size() - 1; i >= 0; i--) {
      Projectile p = shots.get(i);
      if (p.x > e.x-(e.w/2) && p.x < (e.x+(e.w/2))) {
        if (p.y > e.y-(e.h/2) && p.y < (e.y+(e.h/2))) {
          shots.remove(i);
          spinners.remove(j);
        }
      }
    }
    if (e.y > 600) {
      spinners.remove(j);
      lives--;
    }
  }
}
 
public class Sprite {
  boolean alive = true;
  int x;
  int y;
  int w;
  int h;
 
  public Sprite(int xArg, int yArg, int wArg, int hArg) {
    x = xArg;
    y = yArg;
    w = wArg;
    h = hArg;
  }
}
 
public class Player extends Sprite {
 
  int xSpeed;
 
  public Player(int xArg, int yArg, int wArg, int hArg, int speed) {
    super(xArg, yArg, wArg, hArg);
    xSpeed = speed;
  }
 
  public void draw() {
    if (super.alive) {
      fill(color(100, 100, 200));
      rect(super.x, super.y, super.w, super.h);
    }
  }
 
  public void moveLeft() {
    super.x = super.x-xSpeed;
  }
 
  public void moveRight() {
    super.x = super.x+xSpeed;
  }
 
  public Projectile shoot() {
    return (new Projectile(super.x+(super.w/2), super.y));
  }
}
 
public class Enemy extends Sprite {
 
  int ySpeed;
  PImage img;
 
  public Enemy(int xArg, int yArg, int wArg, int hArg, int speed, PImage imgArg) {
    super(xArg, yArg, wArg, hArg);
    ySpeed = speed;
    img = imgArg;
  }
 
  public void draw() {
    if (super.alive) {
      image(img, super.x, super.y, super.w, super.h);
      super.y = super.y + ySpeed;
 
      if (super.y < 0) {
        alive = false;
      }
    }
  }
}
 
 
public class Projectile extends Sprite {
  public Projectile(int x, int y) {
    super(x, y, 5, 25);
  }
  private void draw() {
    if (alive) {
      fill(color(150, 0, 0));
      rect(super.x, super.y, super.w, super.h, 25);
      super.y = super.y - 5;
    }
  }
}
