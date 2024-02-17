# AnimToTextureHelpers

Originally a fork of the excellent work from Kromond. 
But changes introduced in Unreal Engine 5.2 broke it up.
This branch is what I did for Unreal Engine 5.3.1, but there were an update in the original repo of Kromond, maybe you need to look at it : [https://github.com/kromond/AnimToTextureHelpers]

## Approach

I used the assets contained in the AnimToTextureContent Plugins Folder shipped with Unreal Engine 5.3.1.
![Alt text](image-7.png)

I have created copy of them, modified it and add those modified items in this GIT Repository.

Ultimately, the crowd is created using the blueprint : BP_Crowd_PCG

## Steps

### Data Asset

Create a copy of DA_Empty. In the scenario below, I created one named DA_Lewis (Lewis is a Maximo character that I'm using)

Set the Skeletal Mesh

and then run the Blueprint utility
![Alt text](image-14.png)

if that's successful you will see the following message :

![Alt text](image-15.png)


You need to save the newly created content :
![Alt text](image-16.png)

### Review the data asset and add the animations in the Datasset

Once done you can open the Data asset, and notice that the Static Mesh has been addded. 

![Alt text](image-13.png)

![Alt text](image-17.png)

### Add the animations in the Datasset

Add the animations in the dataasset. Those will be use to create the virtual texture.

![Alt text](image-18.png)

### Update the material

Select "Use Material Attributes":
![Alt text](image-20.png)

And then connect properly the nodes.
![Alt text](image-19.png)


### Look the static mesh, and see the materials used

Look at the materials used in the Static Mesh your are using. 
![Alt text](image-4.png)
You will need to instantiate them in the next step

### Create material instances on those materials
Right click the material and create a new instance
![Alt text](image-5.png)

Do the same for hairs

### Edit the material instances
In details tab
![Alt text](image.png)

Select the ML_boneanimation material available in Plugings:
![Alt text](image-6.png)

Select the texture parameters values :

![Alt text](image-1.png)

Copy the texture (UE5.3.1 crashes if there are no existing texture in the data asset, therefore we need to create placeholders for them)

### Edit BP_AnimToTexture so that it has the correct material instances

Edit the blueprint utility BP_AnimToTexture with the correct material instances values.

For body:
![Alt text](image-8.png)

For hairs:
![Alt text](image-9.png)

### Execute BP_AnimToTexture


### Update and Execute BP_AnimToTextureMat

Make sure that the proper material are defined

### Create Actors that will be placed in the PCG

Copy BP_InstancedStaticMeshBaseWithAutoPlay
And set it up with the proper Dataset

![Alt text](image-21.png)

Set up the Static Mesh, and Instanciated Materials

![Alt text](image-22.png)

### Edit PCG Graph

Edit the PCG graph to add your own actors
![Alt text](image-11.png)
