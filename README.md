# AnimToTextureHelpers

Originally a fork of the excellent work from Kromond. 
But changes introduced in Unreal Engine 5.2 broke it up.
This repository is what I did for Unreal Engine 5.3.1, but the there were an update of the original work done by Kromond, maybe you need to look at it.

## Approach

I used the assets contained in the AnimToTextureContent Plugins Folder shipped with Unreal Engine 5.3.1.
![Alt text](image-7.png)

I have created copy of them, modified it and add those modified items in this GIT Repository.

Ultimately, the crowd is created using PCG

## Steps

### Copy material

Go to plugin folder and copy:
the material and the texture

### Create the static mesh from the skeleton mesh using the BP utility BP_CreateSM
Ensure that the data asset is correct in the blueprint
![Alt text](image-3.png)

### Edit the data asset to put the Static Mesh

### Look the static mesh, and see the materials used

Look at the material used in the Static Mesh. 
![Alt text](image-4.png)
You will need to instantiate them in the next step

### Create material instances on those materials
Right click the material and create a new instance
![Alt text](image-5.png)

### Edit the material instances
In details tab
![Alt text](image.png)

Select the ML_bonenamation material available in Plugings:
![Alt text](image-6.png)

Select the texture parameters values :

![Alt text](image-1.png)

copy the texture (UE5.3.1 crashes if there are no existing texture in the data asset, therefore we need to create the place holders)

### Edit BP_AnimToTextureMat so that it has the correct material instances
Edit BP_AnimToTexture so that it has the correct material instances values.


For body
![Alt text](image-8.png)

For hairs
![Alt text](image-9.png)

### Execute BP_AnimToTextureMat


### Create Actors that will be placed in the PCG

### Edit PCG Graph

Edit the PCG graph to add your own actors
![Alt text](image-11.png)
