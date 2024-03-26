


              
  



Code : 
#include<cstdio>
#include <windows.h>
#include<math.h>
#include <vector>
#include <cstdlib>
#define PI 3.14159265358979323846
#include <GL/gl.h>
#include <GL/glut.h>
#include<MMSystem.h>


int x=0,cloudx=0,cloudy=0;
int y=0;


void PointLight(const float x, const float y, const float z,  const float amb, const float diff, const float spec);
void PointLight(const float x, const float y, const float z, const float amb, const float diff, const float spec)
{
  glEnable(GL_LIGHTING);
  GLfloat light_ambient[] = { amb,amb,amb, 1.0 };
  GLfloat light_position[] = {-0.9,.9,0, 0.0 };
  glLightfv(GL_LIGHT0, GL_AMBIENT, light_ambient);
  glLightfv(GL_LIGHT0, GL_POSITION, light_position);
  glEnable(GL_LIGHT0); //enable the light after setting the properties
}


GLfloat position = 0.0f;
GLfloat speed = 0.1f;






GLfloat position1 = 1.0f;
GLfloat speed1 =-0.5f;
void boat2(int value)
{
   if(position1 <- 1.0)
        position1 = 9.0f;


    position1 += speed1;


        glutPostRedisplay();


        glutTimerFunc(100, boat2, 0);
}




GLfloat position2 = 0.0f;
GLfloat speed2 =-0.01f;
void sunn(int value)
{
   if(position2 > 1.0)
        position2 = 0.0f;


    position2 += speed2;


        glutPostRedisplay();


        glutTimerFunc(100, sunn, 0);
}




GLfloat position3 = 0.0f;
GLfloat speed3 =0.1f;
void cloud(int value)
{
   if(position3>1.0)


        position3= -1.0f;


    position3 += speed3;


        glutPostRedisplay();


        glutTimerFunc(300,cloud, 0);
}








void cloudr(int h, int k, int rx, int ry, int R, int G, int B) // Works 
{ 
    // glClear(GL_COLOR_BUFFER_BIT); // Clear the color buffer with current clearing color 
    glColor3ub(R, G, B); 
    glBegin(GL_POLYGON); 
    for (int i = 1; i <= 360; i++)                                                    // 360 kon 
    {                                                                                 //(x=position+radius x(150))    (y=position+radius y(150))   //// y point=sin main point ; x point=cos main point 
        glVertex2f(h + rx * cos(3.14159 * i / 180), k + ry * sin(3.14159 * i / 180)); // main point + radius 
    }                                                                                 // 3.14159*i/180   convert degree to radian 
    glEnd(); 
}






void circle(float x,float y, float rd, int r, int g, int b)
{
    float x1,y1,x2,y2;
    float radius=rd;
    x1=x;
    y1=y;
    glBegin(GL_TRIANGLE_FAN);
    glColor3ub(r,g,b);
    glVertex2f(x1,y1);
    float angle;
    for (angle=0;angle<=360;angle+=0.5)
    {
        x2 = x1+sin((angle*3.1416)/180)*radius;
        y2 = y1+cos((angle*3.1416)/180)*radius;
        glVertex2f(x2,y2);
    }
    glEnd();
}






void river() {                              // River Function 




        glBegin(GL_QUADS);
    glColor3ub(38, 154, 214);
        glVertex2f(-20.0f, -20.0f);
        glVertex2f(-20.0f, 6.0f);
        glVertex2f(20.0f, 6.0f);
        glVertex2f(20.0f, -20.0f);
        glEnd();




}














void house(){                                     //House Function 
        glBegin(GL_QUADS);
        glColor3ub(220, 0, 0);
        glVertex2f(-4.0f, 0.0f);
        glVertex2f(-4.0f, 4.0f);
        glVertex2f(-11.0f, 4.0f);
        glVertex2f(-11.0f, 0.0f);


        glEnd();


        glBegin(GL_QUADS);
        glColor3ub(194, 102, 255);
        glVertex2f(-11.0f, 4.0f);
        glVertex2f(-4.0f, 4.0f);
        glVertex2f(-6.0f, 6.0f);
        glVertex2f(-13.0f, 6.0f);


        glEnd();


        glBegin(GL_QUADS);
        glColor3ub(210, 105, 30);
        glVertex2f(-9.0f, 2.0f);
        glVertex2f(-9.0f, 0.0f);
        glVertex2f(-6.0f, 0.0f);
        glVertex2f(-6.0f, 2.0f);


        glEnd();


        glBegin(GL_QUADS);
    glColor3ub(210,180,140);
    glVertex2f(-7.5f,2.0f);
    glVertex2f(-7.5f,0.0f);
    glVertex2f(-7.25f,0.0f);
    glVertex2f(-7.25f,2.0f);


    glEnd();


        glBegin(GL_QUADS);
        glColor3f(0.0f, 0.0f, 1.0f);
        glVertex2f(-11.0f, 4.0f);
        glVertex2f(-15.0f, 4.0f);
        glVertex2f(-15.0f, 0.0f);
        glVertex2f(-11.0f, 0.0f);


        glEnd();


        glBegin(GL_QUADS);
        glColor3ub(210, 105, 30);
        glVertex2f(-14.0f, 3.0f);
        glVertex2f(-14.0f, 1.0f);
        glVertex2f(-12.0f, 1.0f);
        glVertex2f(-12.0f, 3.0f);


        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.0f, 1.0f);
        glVertex2f(-15.0f, 4.0f);
        glVertex2f(-13.0f, 6.0f);
        glVertex2f(-11.0f, 4.0f);


        glEnd();


}




void grass(){                          // grass function 
    glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-1.5f, -18.0f);
        glVertex2f(-0.5f, -18.0f);
        glVertex2f(-1.0f, -17.0f);
        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-7.0f, -7.0f);    
        glVertex2f(-6.5f, -8.0f);
        glVertex2f(-7.5f, -8.0f);
        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(2.0f, -15.0f);
        glVertex2f(1.5f, -16.0f);
        glVertex2f(2.5f, -16.0f);
        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-2.0f, -14.0f);
        glVertex2f(-2.5f, -13.0f);
        glVertex2f(-3.0f, -14.0f);
    glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(1.0f, -4.0f);
        glVertex2f(0.5f, -5.0f);
        glVertex2f(1.5f, -5.0f);
        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-9.5f, -3.0f);
        glVertex2f(-9.0f, -4.0f);
        glVertex2f(-10.0f, -4.0f);
        glEnd();






        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-14.5f, -10.0f);
        glVertex2f(-14.0f, -11.0f);
        glVertex2f(-15.0f, -11.0f);
        glEnd();






        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-17.0f, -5.0f);
        glVertex2f(-16.5f, -6.0f);
        glVertex2f(-17.5f, -6.0f);
        glEnd();






        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-18.5f, -17.0f);
        glVertex2f(-18.0f, -18.0f);
        glVertex2f(-19.0f, -18.0f);
        glEnd();






        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-13.5f, -5.0f);
        glVertex2f(-13.0f, -6.0f);
        glVertex2f(-14.0f, -6.0f);
        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-17.5f, -8.0f);
        glVertex2f(-17.0f, -9.0f);
        glVertex2f(-18.0f, -9.0f);
        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-10.5f, -10.0f);
        glVertex2f(-10.0f, -11.0f);
        glVertex2f(-11.0f, -11.0f);
        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-14.5f, -17.0f);
        glVertex2f(-14.0f, -18.0f);
        glVertex2f(-15.0f, -18.0f);
        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-1.5f, -1.0f);
        glVertex2f(-1.0f, -2.0f);
        glVertex2f(-2.0f, -2.0f);
        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3f(0.0f, 0.5f, 0.0f);
        glVertex2f(-4.5f, -18.0f);
        glVertex2f(-4.0f, -19.0f);
        glVertex2f(-5.0f, -19.0f);
        glEnd();


}




void fence()                   // fench function 
{
    glLineWidth(4);


    glBegin(GL_LINES);
    glColor3ub(255, 255, 102);
    glVertex2f(-15.0f,4.0f);
    glVertex2f(-20.0f,4.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-15.0f,3.5f);    // fench left side first row 
    glVertex2f(-20.0f,3.5f);




    glColor3ub(255, 255, 102);
    glVertex2f(-15.0f,3.0f);   // fench left side 2nd row 
    glVertex2f(-20.0f,3.0f);




    glColor3ub(255, 255, 102);
    glVertex2f(-15.0f,2.5f);   // fench left side 3rd  row 
    glVertex2f(-20.0f,2.5f);




    glColor3ub(255, 255, 102);
    glVertex2f(-15.0f,2.0f);    // fench left side 4th row 
    glVertex2f(-20.0f,2.0f);




    glColor3ub(255, 255, 102);
    glVertex2f(-15.0f,1.5f);    // fench left side 5th row 
    glVertex2f(-20.0f,1.5f);




    glColor3ub(255, 255, 102);
    glVertex2f(-15.0f,1.0f);    // fench left side 6th row 
    glVertex2f(-20.0f,1.0f);




    glColor3ub(255, 255, 102);
    glVertex2f(-15.0f,0.5f);    // fench left side last row 
    glVertex2f(-20.0f,0.5f);




    glColor3ub(255, 255, 102); 
    glVertex2f(-15.5f,4.5f);  // fench left side right 1st column
    glVertex2f(-15.5f,0.0f);




    glColor3ub(255, 255, 102);
    glVertex2f(-16.0f,4.5f);   // fench left side right 2nd column
    glVertex2f(-16.0f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-16.5f,4.5f);    // fench left side right 3rd column
    glVertex2f(-16.5f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-17.0f,4.5f);   // fench left side right 4th column
    glVertex2f(-17.0f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-17.5f,4.5f);   // fench left side right 5th column
    glVertex2f(-17.5f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-18.0f,4.5f);   // fench left side right 6th column
    glVertex2f(-18.0f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-18.5f,4.5f);  // fench left side right 7th column
    glVertex2f(-18.5f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-19.0f,4.5f);
    glVertex2f(-19.0f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-19.5f,4.5f);
    glVertex2f(-19.5f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-0.0f,4.0f);
    glVertex2f(-4.0f,4.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-0.0f,3.5f);
    glVertex2f(-4.0f,3.5f);


    glColor3ub(255, 255, 102);
    glVertex2f(-0.0f,3.0f);
    glVertex2f(-4.0f,3.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-0.0f,2.5f);
    glVertex2f(-4.0f,2.5f);


    glColor3ub(255, 255, 102);
    glVertex2f(-0.0f,2.0f);
    glVertex2f(-4.0f,2.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-0.0f,1.5f);
    glVertex2f(-4.0f,1.5f);


    glColor3ub(255, 255, 102);
    glVertex2f(-0.0f,1.0f);
    glVertex2f(-4.0f,1.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-0.0f,0.5f);
    glVertex2f(-4.0f,0.5f);




    glColor3ub(255, 255, 102);
    glVertex2f(-3.5f,4.5f);
    glVertex2f(-3.5f,0.0f);




    glColor3ub(255, 255, 102);
    glVertex2f(-3.0f,4.5f);
    glVertex2f(-3.0f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-2.5f,4.5f);
    glVertex2f(-2.5f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-2.0f,4.5f);
    glVertex2f(-2.0f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-1.5f,4.5f);
    glVertex2f(-1.5f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-1.0f,4.5f);
    glVertex2f(-1.0f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(-0.5f,4.5f);
    glVertex2f(-0.5f,0.0f);


    glColor3ub(255, 255, 102);
    glVertex2f(0.0f,4.5f);
    glVertex2f(0.0f,0.0f);


    glEnd();
}










void straw(){                        // Straw Funcion
        glBegin(GL_POLYGON);
        glColor3ub(240, 135, 15);
        glVertex2f(-16.0f, 0.0f);
        glVertex2f(-16.0f, 2.5f);
        glVertex2f(-19.0f, 2.5f);
        glVertex2f(-19.0f, 0.0f);


        glEnd();


        glBegin(GL_POLYGON);
    glColor3ub(240, 135, 15);
    glVertex2f(-18.5f, 3.5f);
        glVertex2f(-16.5f, 3.5f);
        glVertex2f(-16.0f, 2.5f);
        glVertex2f(-19.0f, 2.5f);


        glEnd();


        glBegin(GL_TRIANGLES);
        glColor3ub(240, 135, 15);
        glVertex2f(-18.5f, 3.5f);
        glVertex2f(-16.5f, 3.5f);
        glVertex2f(-17.5f, 5.0f);


        glEnd();


    glLineWidth(4);
    glBegin(GL_LINES);
        glColor3ub(240, 135, 15);
    glVertex2f(-17.5f,5.5f);
    glVertex2f(-17.5f,0.0f);


    glEnd();




}










void way()                                  // way function 
{
    glBegin(GL_QUADS);
    glColor3ub(153, 153, 102);
    glVertex2f(-9.5f,0.0f);
    glVertex2f(-5.5f,0.0f);
    glVertex2f(-1.0f,-5.0f);
    glVertex2f(-3.5f,-7.0f);


    glEnd();


    glBegin(GL_QUADS);
    glColor3ub(153, 153, 102);
    glVertex2f(-3.5f,-7.0f);
    glVertex2f(-3.5f,-8.5f);
    glVertex2f(-0.75f,-9.0f);
    glVertex2f(-1.0f,-5.0f);


    glEnd();


    glBegin(GL_QUADS);
    glColor3ub(153, 153, 102);
    glVertex2f(-3.5f,-7.0f);
    glVertex2f(-0.75f,-9.0f);
    glVertex2f(-9.0f,-20.0f);
    glVertex2f(-14.0f,-20.5f);


    glEnd();




}




void sky(){
        glBegin(GL_QUADS);
    glColor3ub(51, 204, 255);
        glVertex2f(-20.0f, 20.0f);
        glVertex2f(-20.0f, 6.0f);
        glVertex2f(20.0f, 6.0f);
        glVertex2f(20.0f, 20.0f);


        glEnd();
}














void tree(){                                     // Tree Function 


    glBegin(GL_QUADS);
        glColor3ub(128, 0, 0);
        glVertex2f(-3.0f, 0.0f);                    // Tree gach 
        glVertex2f(-1.0f, 0.0f);
        glVertex2f(-1.0f, 7.0f);
        glVertex2f(-3.0f, 7.0f);


        glEnd();




        cloudr( -3,  8, 1, 1, 7, 122, 5); 
    cloudr( -4,  9, 1, 1, 7, 122, 5); 
    cloudr( -3,  10, 1, 1,7, 122, 5); 
        cloudr( -3,  11, 1, 1,7, 122, 5);
        cloudr( -2,  11, 1, 1,7, 122, 5); 
    cloudr( -1,  9, 1, 1,7, 122, 5); 
    cloudr( 0,  11, 1, 1, 7, 122, 5);                   // tree leaf circle  
    cloudr( 0,  10, 1, 1, 7, 122, 5); 
    cloudr( 0,  10, 2, 1, 7, 122, 5); 
    cloudr( -1,  9, 2, 1, 7, 122, 5); 
    cloudr( 0,  8, 1, 1, 7, 122, 5); 
    cloudr( -1,  8, 1, 1, 7, 122, 5); 
    cloudr( -2,  8, 1, 1, 7, 122, 5); 
    cloudr( -2,  7, 1, 1, 7, 122, 5); 
    cloudr( -2,  12, 1, 1, 7, 122, 5); 
    cloudr( -1,  12, 1, 1, 7, 122, 5); 
    cloudr( -3,  12, 1, 1, 7, 122, 5); 
    cloudr( -4,  10, 1, 1, 7, 122, 5); 
    cloudr( -4,  8, 1, 1, 7, 122, 5); 
    cloudr( -1,  8, 1, 1, 7, 122, 5); 


        


}


void ground(){


        glBegin(GL_TRIANGLES);
        glColor3ub(51, 255, 51);
        glVertex2f(0.0f,0.0f);
        glVertex2f(4.0f,-5.0f);
        glVertex2f(0.0f, -10.0f);


        glEnd();


    glBegin(GL_QUADS);
        glColor3ub(51, 255, 51);
        glVertex2f(-20.0f, 0.0f);
        glVertex2f(0.0f, 0.0f);
        glVertex2f(0.0f, -20.0f);
        glVertex2f(-20.0f,-20.0f);


        glEnd();




        glBegin(GL_TRIANGLES);
        glColor3ub(51, 255, 51);
        glVertex2f(0.0f,-20.0f);
        glVertex2f(4.0f,-15.0f);
        glVertex2f(0.0f, -10.0f);


        glEnd();
}








void boat(int x, int y){                    


        glBegin(GL_QUADS);
        glColor3ub(165, 42, 42);
        glVertex2f(x+3.0f, y+-12.0f);
        glVertex2f(x+5.0f, y+-14.0f);
        glVertex2f(x+8.0f, y+-14.0f);
        glVertex2f(x+10.0f,y+ -12.0f);


        glEnd();


        glBegin(GL_QUADS);
        glColor3ub(10, 245, 206);
        glVertex2f(x+3.5f, y+-11.0f);
        glVertex2f(x+3.75f,y+ -11.0f);
        glVertex2f(x+3.75f,y+-16.0f);
        glVertex2f(x+3.5f, y+-16.0f);


        glEnd();
}










void cloud()
{
    glColor3d(1,0,0);
    glPushMatrix();
    glTranslatef(position3,0.0f, 0.0f);


    glBegin(GL_QUADS);
    glColor3ub(10, 92, 20);                 // 1st Bird Function 
    glVertex2f(-10.f, 18.0f);
    glVertex2f(-9.0f,19.0f);
    glVertex2f(-8.0f, 18.0f);
    glVertex2f(-7.0f, 19.0);
    glEnd();




    glBegin(GL_QUADS); 
    glColor3ub(10, 92, 20);                // 2nd Bird Function 
    glVertex2f(-13.f, 15.0f);
    glVertex2f(-12.0f,16.0f);
    glVertex2f(-11.0f, 15.0f);
    glVertex2f(-10.0f, 16.0);
    glEnd();




    glPopMatrix();






//    glFlush();
}


void boat2(){


    glColor3d(1,0,0);


    glPushMatrix();


    glTranslatef(position,0.0f, 0.0f);


        glBegin(GL_QUADS);
        glColor3ub(139, 0, 0);
        glVertex2f(5.0f, 3.0f);
        glVertex2f(7.0f, 1.0f);
        glVertex2f(10.0f,1.0f);
        glVertex2f(12.0f, 3.0f);


        glEnd();


        glBegin(GL_QUADS);
        glColor3ub(255, 215, 0);


        glVertex2f(7.0f, 5.0f);
        glVertex2f(7.0f, 3.0f);
        glVertex2f(10.0f,3.0f);
        glVertex2f(10.0f, 5.0f);


        glEnd();




    glPopMatrix();


        glutSwapBuffers();
}


void update(int value) {  // Dynamic Boat Function 


    if(position <-2.0)
        position = 1.0f;


    position -= speed;


        glutPostRedisplay();




        glutTimerFunc(200, update, 0);
}




void handleMouse(int button, int state, int x, int y) {  // Boat Dynamic Function with speed 
        if (button == GLUT_LEFT_BUTTON)
        {        speed += 0.01f;
                        }
if (button == GLUT_RIGHT_BUTTON)
        {speed -= 0.1f;   }
glutPostRedisplay();
}






void DrawSphere()
{
    glColorMaterial ( GL_FRONT_AND_BACK, GL_AMBIENT_AND_DIFFUSE ) ;
    glEnable ( GL_COLOR_MATERIAL ) ;
    glColor4f(1.0f, 0.0f, 0.0f, 0.0f);
    glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
    glEnable(GL_DEPTH_TEST);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    PointLight(0,0,0.7, 0.4, 0.8, 0);


   


    house();
    //boat(0,0);
    //boat1();
    tree();
        //tree1();
    straw();
    fence();
    way();
    //stars();
    grass();
    ground();
    river();
    //hill();
    cloud();
    glPushMatrix();
    glTranslatef(0.0f,position2, 0.0f);
    //sun();
    glPopMatrix();
    // glFlush();
    glLoadIdentity();
    glutSwapBuffers();


}


void display() {
        glClearColor(0.0f, 0.0f, 0.0f, 1.0f);
        glClear(GL_COLOR_BUFFER_BIT);
        glMatrixMode(GL_PROJECTION);
        glLoadIdentity();
        glLineWidth(2);










    sky();
    //hill();


        
        cloudr(  15,  15, 2, 2, 236, 214, 70); 


        cloudr(cloudx + 10, cloudy + 10, 1, 1, 255, 255, 255); 
    cloudr(cloudx + 11, cloudy + 10, 1, 1, 255, 255, 255); 
    cloudr(cloudx + 11, cloudy + 11, 1, 1, 255, 255, 255); 
        
        cloudr(cloudx - 10, cloudy + 10, 1, 1, 255, 255, 255); 
    cloudr(cloudx - 11, cloudy + 10, 1, 1, 255, 255, 255); 
    cloudr(cloudx - 11, cloudy + 11, 1, 1, 255, 255, 255); 
 
    river();
    boat2();
    fence();
    straw();
    ground();
    way();
    grass();
    glPushMatrix();
    //sun();
    glTranslatef(position1,0.0f, 0.0f);
    //boat1();
    cloud();
    glPopMatrix();
    boat(0,10); // small boat 
    boat(0,0);  // small boat 
    tree();
        //tree1();
    house();








        glFlush();
        glutSwapBuffers();






}


void cloudUpdate(int val) 
{ 
 
    cloudx++;
        if(cloudx == 30)
        {
                cloudx = -10;
        }
 
   
    glutPostRedisplay(); 
    glutTimerFunc(200, cloudUpdate, 0); 
}






/* Main function: GLUT runs as a console application starting at main()  */
int main(int argc, char** argv) {
        glutInit(&argc, argv);
        glutInitWindowSize(1400, 750);
        glutInitWindowPosition(50,50);       // Initialize GLUT
        glutCreateWindow("VILLAGE SCENARIO 202-15-3850");  // Create window with the given title
        glutDisplayFunc(display);
    gluOrtho2D(-20,20,-20,20);
        //glutKeyboardFunc(handleKeypress1);
    glutMouseFunc(handleMouse);  // Boat dynamic function call
        glutTimerFunc(100, update, 0); // boat dynamic function call 
        glutTimerFunc(100, cloud, 0);
        glutTimerFunc(100, sunn, 0);
        glutTimerFunc(100, cloudUpdate, 0);
        glutMainLoop();                 // Enter the event-processing loop
        return 0;
}














































