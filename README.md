# TELLASTORY
/*
 * This program tells a graphical story in 4 frames.
 */

/* 
 * Draws the first scene on the canvas and outputs the first
 * section of text for the story.
 */
function drawScene1(){
    // IMPLEMENT THIS FUNCTION
    println("This is scene 1");
    removeAll();
    drawBackground();
    drawJasmin(250,195);
    drawFrisbee(275,230);
    println("Jasmin was waiting around in the park.");
}

/* 
 * Draws the second scene on the canvas and outputs the second
 * section of text for the story.
 */
function drawScene2(){
    // IMPLEMENT THIS FUNCTION
    println("This is scene 2");
    removeAll();
    drawBackground();
    drawJasmin();
    drawLine(80,160,110,160,5,Color.orange);
    drawCircle(110,160,5,Color.red);
    drawGirl();
    drawFrisbee(275,230);
    println("Jasmin really wanted to make friends, so she asked the girl to pass the frisbee to her");
    
}

/* 
 * Draws the third scene on the canvas and outputs the third
 * section of text for the story.
 */
function drawScene3(){
    // IMPLEMENT THIS FUNCTION
    println("This is scene 3");
    drawBackground();
    drawJasmin();
    drawGirl();
    drawRect(10,50,250,195,Color.blue);
    drawFrisbee(320,120);
    println("The girl immediately threw it the opposite direction");
    
}

/* 
 * Draws the fourth scene on the canvas and outputs the fourth
 * section of text for the story.
 */
function drawScene4(){
    // IMPLEMENT THIS FUNCTION
    println("This is scene 4");
    removeAll();
    drawBackground();
    jasminTurned();
    drawGirl();
    drawFrisbee(320,120);
    println("Jasmin was really upset and she started crying");
    println("THE END");
    
    
}

function drawRect(width,height,x,y,color){
    var rect = new Rectangle(width,height);
    rect.setPosition(x,y);
    rect.setColor(color);
    add(rect);

}

function drawCircle(x,y,radius,color){
    var circle = new Circle(radius);
    circle.setPosition(x,y);
    circle.setColor(color);
    add(circle);
}

//function drawCircle(x, y, radius, color){
    //var circle = new Circle(radius);
    //var x = getWidth() / 2;
    //var y = getHeight() / 2;
    //circle.setPosition(x, y);
    //circle.setColor(color);
    //add(circle);
    
    
//}

//function drawCircle(x, y, radius, color){
    //var circle = new Circle(radius);
    //circle.setPosition(x, y);
    //circle.setColor(color);
    //add(circle);
    
//}



function drawLine(x1,y1,x2,y2,width,color){
    var line = new Line(x1, y1, x2, y2);
    line.setLineWidth(width);
    line.setColor(color);
    add(line);
}

function drawJasmin(){
    drawCircle(100,150,30,Color.orange);
    drawRect(10,20,95,170,Color.orange);
    drawRect(40,80,81,190,Color.yellow);
    drawRect(40,30,81,270,Color.cyan);
    drawCircle(90,140,3,Color.blue);
    drawCircle(110,140,3,Color.blue);
    drawRect(10,50,72,190,Color.orange);
    drawRect(10,50,120,190,Color.orange);
    drawLine(90,160,110,160,3,Color.red);
    drawLine(100,270,100,300,3,Color.black);
    
}

function drawBackground(){
    drawRect(getWidth(),200,0,300,Color.green);
    drawRect(getWidth(),300,0,0,Color.blue);
    drawCircle(getWidth(),20,50,Color.yellow);
    
}

function drawGirl(x,y){
    drawCircle(250,160,25,Color.orange);
    drawRect(10,20,223,180,Color.orange);
    drawRect(40,70,210,195,Color.purple);
    drawRect(40,40,210,260,Color.white);
    drawLine(230,270,230,300,3,Color.black);
    drawCircle(220,155,3,Color.blue);
    drawCircle(240,155,3,Color.blue);
    drawRect(10,50,250,195,Color.orange);
    drawRect(10,50,200,195,Color.orange);
    drawLine(220,170,240,170,3,Color.red);
}

function drawFrisbee(x,y){
    drawCircle(x,y,30,Color.orange);
    drawCircle(x,y,20,Color.yellow);

}

function jasminTurned(){
    drawCircle(100,160,20,Color.orange);
    drawRect(10,20,95,170,Color.orange);
    drawRect(40,60,81,190,Color.yellow);
    drawRect(40,60,81,240,Color.cyan);
    drawCircle(90,160,3,Color.blue);
    drawRect(10,50,100,190,Color.orange);
    drawLine(90,170,100,170,2,Color.red);
    
}
/**********************************************************
 * This is set up code that makes the story advance from
 * scene to scene. Feel free to check out this code and
 * learn how it works!
 * But be careful! If you modify this code the story might
 * not work anymore.
 **********************************************************/

var sceneCounter = 0;
function start() {
    
    var welcome = new Text("Click to Begin!");
    
    welcome.setPosition(
        getWidth() / 2 - welcome.getWidth() / 2,
        getHeight() / 2
    );
    
    add(welcome);
    
    // Call the drawNextScene function every time the mouse is clicked
    mouseClickMethod(drawNextScene);
}

/*
 * When this function is called the next scene is drawn.
 */
function drawNextScene(){
    sceneCounter++;
    
    if(sceneCounter == 1) {
        drawScene1();
    } else if (sceneCounter == 2) {
        drawScene2();
    } else if (sceneCounter == 3) {
        drawScene3();
    } else {
        drawScene4();
    }
}
