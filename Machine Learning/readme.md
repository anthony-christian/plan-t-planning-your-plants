# Machine Learning 

## Team
- Imaduddin Abdul Karim - M7012J1329
- Euis Amara Putri - M2012F1317

There are 8 classes of plants.

## Dataset
- [Drive](https://drive.google.com/drive/folders/1ajFgqdUiTkwgOUJZMjuOZV8tDweemG49?usp=sharing)

### Applied .tflite to Android
The model in this repository is designed to run on android applications. The following is a documentation guide for using the .tflite model in android studio (We use kotlin)
1. Do instance your model in model variable
   ```
   val model = YourModel.newInstance(this)
   ```
2. Take image in bitmap then insert to image variable
   ```
   val image = TensorImage.fromBitmap(bitmap)
   ```
3. Do prediction on image, use list for descending then give list to outputs variable.
   ```
   val outputs = model.process(image).probabilityAsCategoryList.apply {
      sortByDescending { it.score }
   }
   ```
4. Access outputs[0] for class that have biggest accuracy then give to probability variable
   ```
   val probability = outputs[0]
   ```
