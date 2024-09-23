
# Instance Segmentation and Histogram Comparison

This project was tested with Python 3.10.

## Explanation 
The goal of this project is to correctly identify 5 different people in a long series of images. The 5 people will be identified using 5 test images given. The algorithm will run through 2 folders of images (cam0 and cam1) and identify each of these 5 people in the set of images.

- First, detection of humans in images have been done using instance segmentation. This method uses convolutional neural networks to effectively detect persons and segment them from the background.
- The output of the algorithm are masks representing each person that has been segmented from each image.
- These segmented people are run through an algorithm that will calculate their likeness to 5 pre-identigied people using the Histogram Comparison method.
- Using a threshold, we will only keep those top 100 best matches to each of the 5 people.
- The result is saved in the [output](https://github.com/AmyKKiti/OpenCV-Image-Identification-and-Detection/blob/main/output) folder.

More details can be found in the [report](https://github.com/AmyKKiti/OpenCV-Image-Identification-and-Detection/blob/main/Output_Results_Report.pdf).

## Set Up

Follow these simple steps to get your local copy up and running.

1. Download the folder `images.zip` from the google drive link below:
   ```
   https://drive.google.com/file/d/1potC4tmKjvLAlXSmhaGH59u-g5u4qg5-/view?usp=sharing
   ```

2. Extract `images.zip` and place it in the root directory of the repository. Example: The path should be `images\images\cam0` for cam0.

3. Open a command line on the root directory.

4. Create a virtual environment
   ```
   python3 -m venv env
   ```

5. Activate the virtual environment
   ```
   source env/bin/activate
   ```

6. Install code dependencies
   ```
   pip install -r requirements.txt
   pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cpu
   ```
7. If you wish to see the results of the algorithm, delete the contents of the `cam_output/person` folders. Currently it contains the results of the previous run.

## Usage

Run the code with `python main.py`

Note about thresholds: If you wish to see all the 831 images for each person, replace all threshold values by zero.

