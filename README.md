# ICS20-WOLFPACKGAMES
Game that will be shown to the kids.



var starsize =14;
noStroke();
var leftX = 93;
var rightX = 267;
var gem = getImage("cute/GemOrange");
var currentscene =0;
var redxpos = 39;
var greenxpos = 39;
var redthing = getImage("avatars/piceratops-tree");
var greenthing = getImage("avatars/leafers-tree");

  var drawbutton = function () {
    fill(39, 208, 217);
    rect(132, 271, 136, 41, 10);
    fill(255, 0, 0);
    textSize(20);
    text("PLAY!", 174, 297);
  };
    



var drawscene1 = function () {
    currentscene=0;
    background(26, 2, 26);
    textSize(30);
    text("TEMPLE RUN JUNIOR", 50, 100);
    noFill();
    stroke(90, 158, 92);
    strokeWeight(6);
    rect(41, 64, 333, 54, 6);
    strokeWeight(16);
    stroke(247, 234, 247);
    arc(199, 263, 187, 177, 178, 359);
    arc(199, 263, 158, 177, 186, 357);
    arc(199, 263, 134, 178, 189, 351);
    arc(199, 263, 216, 177, 176, 363);
    line(91, 277, 132, 250);
    line(308, 277, 264, 255);
        
        
        for (var x =168;x < 222; x+=13) {
        fill(13, 73, 224);
        image(gem, x, 228, starsize, starsize);
        image(gem, x, 235, starsize, starsize);
        image(gem, x, 242, starsize, starsize);
        }
        
        noStroke();
        drawbutton();
        
  };
  
  var drawscene2 = function() {
    currentscene =1;
    background(35, 13, 74);
    textSize(22);
    fill(232, 93, 116);
    text("CHOOSE YOUR CHARACTER", 50, 100);
    noFill();
    stroke(51, 213, 219);
    strokeWeight(6);
    rect(41, 64, 333, 54, 6);
    ellipse(113, 269, 150, 150);
    ellipse(296, 270, 150, 150);
    strokeWeight(1.5);
    stroke(238, 255, 0);
    //rect(45, 146, 139, 23);
    //rect(226, 146, 139, 23);
    fill(43, 255, 0);
    text("HAYDEN",66, 165);
    text("SOPHIA",248, 164);
    image(greenthing, 52, 198);
    image(redthing, 231, 206);
    //we don't have bitmojis yet, so we are substituting random images for now
    
    noFill();
    rect(88, 362, 58, 20);
    fill(204, 25, 25);
    textSize(15);
    text("NEXT", 97, 378);
    noFill();
    rect(276, 362, 58, 20);
    text("NEXT", 283, 378);
     
};
  
drawscene2();

var level1 = function () {
    currentscene=2;
    noStroke();
background(159, 205, 245);
fill(255, 234, 0);
ellipse(345, 48, 80, 80);
    
    fill(250, 245, 245);
    ellipse(leftX, 82, 73, 59);
    ellipse(leftX+50, 81, 43, 39);
    ellipse(leftX-52, 83, 43, 39);
    
    ellipse(rightX, 58, 73, 59);
    ellipse(rightX+53, 58, 43, 39);
    ellipse(rightX-52, 62, 43, 39);
    
    for (var x =0;x < 400; x+=47) {
    fill(37, 42, 128);
    ellipse(x, 220, 57, 50);
    rect(0, 225, 415, 203);
    }
    
    fill(16, 92, 21);
    triangle(6,682,65,336,56,255);
    triangle(209, 682, 73, 320, 7, 230);
    triangle(300,682, 284,336, 310, 230);
    triangle(333,682,265,336,233,284);
        
        //fish function
        var drawFish = function(centerX, centerY, bodyLength, bodyHeight, bodyColor, tailWidth, tailHeight){
        
    noStroke();
    fill(bodyColor);
    // body
    ellipse(centerX, centerY, bodyLength, bodyHeight);
    // tail
    var tailWidth = bodyLength/4;
    var tailHeight = bodyHeight/2;
    triangle(centerX-bodyLength/2, centerY,
             centerX-bodyLength/2-tailWidth, centerY-tailHeight,
             centerX-bodyLength/2-tailWidth, centerY+tailHeight);
    // eye
    fill(33, 33, 33);
    ellipse(centerX+bodyLength/4, centerY, bodyHeight/5, bodyHeight/5);
    };
    
    drawFish(246, 311, 74, 67, color(133, 13, 109)); 
    drawFish(357, 356, 38, 23, color(222, 138, 11));
    drawFish(346, 259, 41, 20, color(204, 12, 12));
    drawFish(124, 245, 50, 34, color(153, 89, 136));
    drawFish(103, 327, 34, 20, color(217, 240, 88));
    
};


 mouseClicked = function () {
      if (mouseX > 132 && mouseX < 268 && mouseY > 271 && mouseY < 312){
          drawscene2();
      }
      if (mouseX > 88 && mouseX < 146 && mouseY > 58 && mouseY < 382) {
            level1();
            image(greenthing, 39, 100);
            /*draw = function() {
                level1();
                greenxpos +=1;
                image(greenthing, greenxpos, 100);
                
            };*/
       }
       if (mouseX > 276 && mouseX < 334 && mouseY > 362 && mouseY < 382) {
           level1();
           image(redthing, 39, 100);
          /* draw = function() {
               level1();
               redxpos += 1;
                image(redthing, redxpos, 100);
           };*/
           
           
       }
 
      }; 
 

 
drawscene1();
/*mouseClicked=function(){
    if (currentscene === 0){
        drawscene2();
    } else if (currentscene ===1) {
          level1();
          image(getImage("avatars/leafers-tree"), 52, 198);
    }
};*/
