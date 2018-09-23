# GradeRegular
## Summary
Converts images and JFLAP files (.jff) to Verilog. Formal Verification of output is still incomplete.
*NOTE: detction accuracy is not super great. Any help will be appriciated.

## Setup Procedures
1. *Install MiniConda3*: https://conda.io/miniconda.html
2. *Install Python Libraries* (in Conda environment):
  * **conda install pip**
  * **conda install scipy scikit-image ipython**
  * **pip install numpy matplotlib opencv-python nnabla**
3. *Clone Git Repo*: **git clone [this repo url]**
4. Using the programs:
  * Make Verilog from image: **python Image2V.py [input image file]** 

## Drawing Rules
**RULES**: leftmost node is the start state, accept states are double circles, transitions are 0, 1, or Epsilon 
1. State circles must be 10 to 40% of the smaller of the two sides of image (if landscape, then it is the height)
2. All transitions represent one and only one value out of 0, 1, or epsilon
3. For self-loops, the transition label should be written within the loop. \
   For non-self-loops, the transition label should be written close to the destination.
4. Transition line should not cross with another transition line
5. No labels or letters within states.
6. When having 2 lines in parallel, make sure they are not curved and reduce the distance between the two to prevent it from being detected as circle.
7. For accept states (double circle), make sure the inner circle is clearly separated with good distance (10-20% of circle radius).

## Drawing tips (not absolute, but helps detect)
1. Diagram should be written neatly and with thick strokes.
2. Keep the number of nodes low (2-4) so that these do not form near-closed regions.
3. Keep transition labels from touching transition lines.