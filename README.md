# The Project (the algorithm, the purpose, the goal)
Jetson Nano tests. Conducted for learning and the observation of AI.
Provided in my detailed video (https://drive.google.com/file/d/1O7kjKA-4ObZ94ZGNBm3O7jyiFtzmjzWW/view?usp=sharing) my mission and goal is to ascribe the fundamentals of AI classification and learning within the realm of aquatic marine life. My model is the Resnet 18 which contains 18 layers, hence the name. The program or AI that I used is recognized by numerous high-tech companies such as Google, Apple, and Microsoft. This program is referred to python and uses thousands of hours of coding to recognize images and more. The purpose of using this mechanical tool is for the classification and categorization of different marine life, particularly fish and mammals. What my project provides is a label to a particular image given to the trained machine as it was then processed using preceeding images resembling the subjected image. These preceeding images are comformed in a specific dataset designed to express fish and mammalian sea creatures. The given dataset is presented here: https://www.kaggle.com/datasets/vencerlanz09/sea-animals-image-dataste. 
Carrying this process and procedure through can allows scientists and researchers to better classify the unique and diverse nature of fish and mammal sea creatures. This is not only beneficial for identifying different earthly ocean species but to potentially accurately decrypt marine life on other worlds for the better of understanding and studying them. 
# The Steps to Completing this Process
1. Make sure your nano is connect through SSH networks
2. Download this dataset that I provided in my summary: https://www.kaggle.com/datasets/vencerlanz09/sea-animals-image-dataste
3. Create an ocean_creatures folder in VSC that splits into train, test, and val folders. In each of these three folders, create a fish and mammal folder.
4. Sort the pictures and folders into the mammal and fish folders given that being their classification.
5. The train folder should contain 90% of all the photos you wish to use in your experiment, while the rest have 5% each (test and val). 
6. Convert the downloaded folders that you've created with the dataset into the replicated folders in the VSC (or another code software).
7. Run the command ./docker/run.sh in your terminal (make sure you are in the jetson-inference folder)
8. Navigate to jetson-inference/python/training/classification to start the following processes: a. run this command python3 train.py --model-dir=models/ocean_creatures data/ocean_creatures to commence your model training (you can also use --batch-size=NumberOfBatchFiles --workers=NumberOfWorkers --epochs=NumberOfEpochs or Ctr+C to stop and specify the number of epochs you wish to use, hit --resume to resume the process)
9. Run the command python3 onnx_export.py --model-dir=models/ocean_creatures to complete the export of the model.
10. Now use ls models/ocean_creatures/ for clarification of the presence of the model
11. After clarifying, set the NET and DATASET variables using NET=models/ocean_creatures and DATASET=data/ocean_creatures.
12. Now run this command and let the machine do the rest imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/mammal/mammal/2170403941_8cfe75dbd2_o.jpg mammalian.jpg (you can customize the end variable "mammalian.jpg" and choose another file and directory for the "test/mammal/mammal/file.jpg" but make sure to type the mammal or fish folder twice.
# References:
1. VSC (Visual Studio Code)
2. NumPy
3. Pytorch
4. video link: https://drive.google.com/file/d/1O7kjKA-4ObZ94ZGNBm3O7jyiFtzmjzWW/view?usp=drive_link 
5. kaggle dataset: https://www.kaggle.com/datasets/vencerlanz09/sea-animals-image-dataste
