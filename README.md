## A simple OCR for recognising lower-case and upper-case English alphabets

This is the OCR software we built as our B.Tech. 6th semester academic project.

The features used by us include: 
```markdown
1. **Zoning** : To analyze the densities of the points and some strokes in different regions of  the image by dividing it into four non-overlapping zones (_upper left, upper right, lower left and lower right_) and form the features.
2. **Crossings** : To count the number of transitions from background to foreground pixels along vertical and horizontal lines through the character image.
3. **Moments** : To make the process of recognizing an object in an image size translation and rotation independent.
4. **Intersections/Junctions in a character** : To count the number of open end points and junctions from thinned and scaled character image by divided into 16 segments, each of size 25 × 25 pixels wide. For each segment, the number of open end points and junctions are calculated. _Intersection point is defined as a pixel point which has more than two neighboring pixels in 8-connectivity while an open end has exactly one neighbor pixel._

When combined, these result in a total of 67 features, where the **Junction points in a character** was found to be the most relevant while the **Moments** was the least. 
```
For further details on feature extraction techniques, readers are kindly referred to see [A Detailed Review of Feature Extraction in Image Processing Systems](http://ieeexplore.ieee.org/document/6783417/). 

`/tempdata1` contains the trained images.
`/images` contains the input images to be tested upon.

### For training the data:
` python3 trainingDataSetMaker.py`
### To observe the output of the recognised image:
` python3 main1.py`
### To observe the accuracy:
` python3 main.py`
### Executing the bash script for a combined output of above two commands:
` ./ocr.sh "/path/to/input/image"`

All the code has been implemented on our own.
Highest accuracy achieved so far : _90% on Voting of classifiers_ and can further be increased by addition of more reliable features.


[Saurav Jha](https://www.linkedin.com/in/saurav-mnnit/).
