# Exp02-RollABall

## Aim:
### To develop a 3D application to roll a ball in unity

## Algorithm:
 Step1: File -> Scene -> Select the scene -> Save as-> New folder(Scenes)-> File name (MiniGame)

 Step2: Heirarchy -> 3D Object-> Plane 
 [ Right side-> Inspector-> Change the name of plane (Name: Ground) ,Transform -> Reset ,Edit -> FrameSelected ]

 Step3: Scale the ground by giving the scaling value as x=4 y=1 z=4

 Step 4: Heirarchy -> 3D Object-> Sphere [ Right side-> Inspector-> Change the name of plane (Name: Player)
 Transform -> Reset , Edit -> FrameSelected, Transform -> Position -> y=0.5]

 Step5: Hierarchy -> DirectionalLight [ Inspector -> Change the color to white (255,255,255)]

 Step 6: Create a folder in project and name as Materials [Material folder -> Create -> Material (Name: Background)
 Inspector ->Surface Inputs ->BaseMAp (Choose the color) Metallic map-> 0, Smoothness -> 0.25, Drag the Background to the plane and release the mouse
 Material folder -> Create -> Material (Name: Sphere) Inspector ->Surface Inputs ->BaseMAp (Choose the color) Metallic map-> 0,Smoothness -> 0.75,Drag the Sphere material to the ball and release the mouse

Step7: Hierarchy -> Player-> Inspector ->Add component-> Rigidbody

Step8: Create a new script -> Create a folder in project (Name: Scripts) Hierarchy -> Player -> Inspector-> AddComponent-> NewScripts-> PlayerController( Click create and Add), Copy the PlayerController and drag to Script folder, Double click the PlayerController file and type the coding

## Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Code : MonoBehaviour
{
    public float Xforce =5.0f;
       public float Zforce =5.0f;
       public float Yforce =100.0f; 
    // Start is called before the first frame update
    void Start()
    {
       
    }

    // Update is called once per frame
    void Update()
    {
        float X=0.0f,Y=0.0f,Z=0.0f;
        if(Input.GetKey(KeyCode.D))
        {
            X=X-Xforce;

        }
        if(Input.GetKey(KeyCode.A))
        {
            X=X+Xforce;
        }
        if(Input.GetKey(KeyCode.D))
        {
            Z=Z-Zforce;
        }
        if(Input.GetKey(KeyCode.W))
        {
            Z=Z+Zforce;
        }
        if(Input.GetKeyDown(KeyCode.Space))
        {
            Y=Yforce;
        }
        GetComponent<Rigidbody>().AddForce(X,Y,Z);
    }
}
```

## Output:
<img width="1039" height="617" alt="image" src="https://github.com/user-attachments/assets/f5002ee1-09c1-441a-a093-bc77b417bbd2" />

## Result:
Thus, a 3D application for RollABall objects in unity is developed successfully.
