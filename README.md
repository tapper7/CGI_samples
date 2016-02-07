# CGI_samples
<b> sample one: droppin' lerpy balls</b>
/*Algorithm by cwelke @Tapper7.com for Self-Similarity Studios
Last stable build: using Processing API, JDK 1.8, win8.1 5/26/15
Dist under The GNU Public License - compliant with ANSI/ISO std.*/

//note***no draw() - do this once for simplicity, twaeking, debugging
void setup(){
   size(1000,860);
   background(#000000);
   noStroke();
   float dec = 0.7; //decimal/decremnt ratio amt.
   selfS(width*dec, height*dec, 400);//#
}//end setup

//#-the meat of the logic
void selfS(float x, float y, float sz){
   float angle, nx, ny;
   //last int is transparency--rand switches tint
   fill(lerpColor(#FF0000, #800000, random(1)), 300);
   ellipse(x, y, sz, sz);
   float rec = 0.588; //recursion differential
   if(sz > 1){//recurse to base-case::do(while px_sz > 1)
      angle = random(TWO_PI);
      nx = x + sz*rec * sin(angle);
      ny = y + sz*rec * cos(angle);
      selfS(nx, ny, sz*rec);
      angle = random(TWO_PI);
      nx = x + sz*rec * sin(angle);
      ny = y + sz*rec * cos(angle);
      selfS(nx, ny, sz*rec);
      angle = random(TWO_PI);
      nx = x + sz*rec * sin(angle);
      ny = y + sz*rec * cos(angle);
      selfS(nx, ny, sz*rec);
   }//endIF
}//end selfS
