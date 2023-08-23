# FLAME_TO_HACK
Scripts to convert FLAME face model to HACK model(same facial topology as ICT-FaceKit).

## Description
The HACK Model is a head model consists of a base topology along with definitions of facial landmarks, shape blendshapes, expression blendshapes, cervical joints, and pose blendshapes. More informations can be found here in this repo [HACK](https://github.com/ZoneLikeWonderland/HACK-Model)

For some reason, HACK didn't release its texture model. This Repo provides some scripts for converting FLAME's texture to HACK.
My general approach to this issue is as follows:
1. Fit HACK model(optimize shape parameter and pose parameter) to FLAME model, then they have generally the same shape but different mesh.
2. Use KNN to obtain the interpolated pixels and render the HACK mesh to check whether it can be rendered correctly.
3. Once I am sure that Step 2 is ok, I use KNN the get every UV coordinate in FLAME's texture space. It is hard to generate a new UV map using HACK's UV coordinate, so I choose to change HACK's UV coordinate to fit FLAME's texture space.
4. Finally, I render the HACK's shape and color to check it correctness.
5. So, use the modified HACK UV coordinate is just ok. 

Colab Code can be found here:
https://colab.research.google.com/drive/19oOovJ3JY-s1o_NFc9Ht5TFCNByGlCCG?usp=sharing
