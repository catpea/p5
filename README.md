# p5
P5.js Math Tutorial Boilerplate

```JavaScript
function setup() {

  // Define Colors By Mixing Red Green and Blue.
  let black = color(0, 0, 0);
  let red = color(255, 0, 0);
  let green = color(0, 155, 0);
  let blue = color(0, 0, 255);
  let magenta = color(255, 0, 255);
  let cyan = color(50, 155, 155);
  
  // Canvas Size
  let width = 800;
  let height = 600;

  // Prepare Imaginary World
  let horizonCenter = width/2;
  let rootStart = 0
  
  // Define Changes
  let branchLength = 200
  let branchCutPercent = .4;

  // Initialize Variables We Will Use Throughout
  let heightStart = 0;
  let heightMid = null;
  let heightEnd = null;
  let toTheLeft = null;
  let toTheRight = null;

  // Configure P5
  createCanvas(width, height);
  background(220);
  
  // Fix P5 Coordinates, put 0,0 in lower left.
  translate(0, height);
  scale(1, -1);
  
  // Create The Tree Root
  stroke(black);
  heightMid = heightStart + (branchLength/2);
  heightEnd = heightStart + branchLength;
  line(horizonCenter, heightStart, horizonCenter, heightEnd); // root
  
  // First Generation, after the stump.
  stroke(red);
  branchLength = branchLength - (branchLength * branchCutPercent);
  heightStart = heightEnd;
  heightMid = heightStart + (branchLength/2);
  heightEnd = heightStart + branchLength;
  toTheLeft = horizonCenter - branchLength;
  toTheRight = horizonCenter + branchLength;
  line(horizonCenter, heightStart, horizonCenter, heightEnd); // root segment
  line(horizonCenter, heightStart, toTheLeft, heightMid);
  line(horizonCenter, heightStart, toTheRight, heightMid);

  // Second/Green Generation
  stroke(green);
  branchLength = branchLength - (branchLength * branchCutPercent);
  heightStart = heightEnd;
  heightMid = heightStart + (branchLength/2);
  heightEnd = heightStart + branchLength;
  toTheLeft = horizonCenter - branchLength;
  toTheRight = horizonCenter + branchLength;
  line(horizonCenter, heightStart, horizonCenter, heightEnd); // root
  line(horizonCenter, heightStart, toTheLeft, heightMid);
  line(horizonCenter, heightStart, toTheRight, heightMid);
  
  // Third/Blue Generation
  stroke(blue);
  branchLength = branchLength - (branchLength * branchCutPercent);
  heightStart = heightEnd;
  heightMid = heightStart + (branchLength/2);
  heightEnd = heightStart + branchLength;
  toTheLeft = horizonCenter - branchLength;
  toTheRight = horizonCenter + branchLength;
  line(horizonCenter, heightStart, horizonCenter, heightEnd); // root
  line(horizonCenter, heightStart, toTheLeft, heightMid);
  line(horizonCenter, heightStart, toTheRight, heightMid);
  
  // Fourth/Magenta Generation
  stroke(magenta);
  branchLength = branchLength - (branchLength * branchCutPercent);
  heightStart = heightEnd;
  heightMid = heightStart + (branchLength/2);
  heightEnd = heightStart + branchLength;
  toTheLeft = horizonCenter - branchLength;
  toTheRight = horizonCenter + branchLength;
  line(horizonCenter, heightStart, horizonCenter, heightEnd); // root
  line(horizonCenter, heightStart, toTheLeft, heightMid);
  line(horizonCenter, heightStart, toTheRight, heightMid);
  
  // And so on, this part just finishes up the tree...
  for(remainingGenerations = 0; remainingGenerations < 15; remainingGenerations++){
      stroke(cyan);
      branchLength = branchLength - (branchLength * branchCutPercent);
      heightStart = heightEnd;
      heightMid = heightStart + (branchLength/2);
      heightEnd = heightStart + branchLength;
      toTheLeft = horizonCenter - branchLength;
      toTheRight = horizonCenter + branchLength;
      line(horizonCenter, heightStart, horizonCenter, heightEnd); // root
      line(horizonCenter, heightStart, toTheLeft, heightMid);
      line(horizonCenter, heightStart, toTheRight, heightMid);
  }
  
  
  
}

function draw() {
  
}
```
