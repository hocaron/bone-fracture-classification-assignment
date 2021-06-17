# Bone-Fracture-Classification

## 📄Summary
It's  a CNN model that classifies normal bones and fracture bones. Here are the methods I have tried to improve model accuracy.  
Train Data Set : 320 Validation Data Set : 33 Test Data Set : 90

## Normal Bone
![image](https://user-images.githubusercontent.com/66551410/122440694-c67e0d00-cfd7-11eb-8ec4-23383d725ed6.png)

## Fracture Bone
![image](https://user-images.githubusercontent.com/66551410/122440712-cb42c100-cfd7-11eb-89f8-47a1eb9266f3.png)

## Data Agumentation
### Vertical Flip
~~~
    for f in files:
        img = Image.open(train_path+d+'/'+f,'r')
        img = resize(img)
        img = TF.hflip(img)
        r,g,b = img.split() # same levels
        one_img = np.asarray(np.float32(r)/255.0) #choose one
        img = np.asarray([one_img])
        data.append(img)
        label.append(i)
~~~
### Horizontal Flip
~~~
    for f in files:
        img = Image.open(train_path+d+'/'+f,'r')
        img = resize(img)
        img = TF.vflip(img)
        r,g,b = img.split() # same levels
        one_img = np.asarray(np.float32(r)/255.0) #choose one
        img = np.asarray([one_img])
        data.append(img)
        label.append(i)
~~~
## Add layer
~~~
            nn.Conv2d(128, 256, 3),
            nn.LeakyReLU(),
            nn.Conv2d(256, 256, 3),
            nn.LeakyReLU(),
            nn.MaxPool2d(3,2),
~~~

## Dropout
![image](https://user-images.githubusercontent.com/66551410/122441624-ad299080-cfd8-11eb-94a7-a9cb471f48ce.png)

## Others
* Batch size
* Hyper parameter
* Data crop size

## ResNet50
![image](https://user-images.githubusercontent.com/66551410/122442393-7dc75380-cfd9-11eb-9ffa-392364027eff.png)

## Model Accuracy
![image](https://user-images.githubusercontent.com/66551410/122440911-fc22f600-cfd7-11eb-911b-6ff5d2a48f7f.png)

## Block Diagram
![image](https://user-images.githubusercontent.com/66551410/122440985-0e9d2f80-cfd8-11eb-99f7-c27f5fdce203.png)



