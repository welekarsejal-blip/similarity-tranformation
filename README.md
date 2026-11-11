Similarity Transformation

An interactive project that shows how a similarity transformation works using matrices. It includes a Python program (NumPy + Matplotlib) and a web app (HTML, CSS, JavaScript) that you can explore live in the browser.

What is a Similarity Transformation?

A similarity transformation changes the size and position of a figure but not its shape. The new figure is an exact scaled copy of the original:

All angles stay the same.
All sides are multiplied by the same ratio (the scale factor s).

It is made from four operations: uniform scaling, rotation, translation, and an optional reflection.

The Math

Each operation is written as a 3×3 matrix using homogeneous coordinates, where a point (x, y) becomes (x, y, 1).

Operation	Matrix
Scaling S	[[s, 0, 0], [0, s, 0], [0, 0, 1]]
Rotation R	[[cosθ, -sinθ, 0], [sinθ, cosθ, 0], [0, 0, 1]]
Translation T	[[1, 0, tx], [0, 1, ty], [0, 0, 1]]
Reflection F (x-axis)	[[1, 0, 0], [0, -1, 0], [0, 0, 1]]

They combine into one matrix:

M = T · R · F · S
P' = M · P

where P is a point and P' is its image after the transformation.

Project Files
File	Description
similarity_transformation.py	Python version using NumPy for matrices and Matplotlib for plotting
index.html	Interactive web app (single static file, no dependencies)
README.md	This file
Python Version
Requirements
Python 3.8 or newer
NumPy
Matplotlib
Install and run
bash
pip install numpy matplotlib
python similarity_transformation.py

The program prints the transformation matrix and the original and new coordinates, then opens a graph with the original shape in blue and the transformed shape in red. It also checks that every side ratio equals s and that all angles are unchanged.

Change the input

Edit these values in the script and run it again:

python
original = np.array([[1, 1], [4, 1], [2, 3]], dtype=float)
s = 1.5          # scale factor
theta = 45       # rotation angle in degrees
tx, ty = 3, 2    # translation
reflect = False  # True to also reflect across the x-axis
Web App

Open index.html in any browser, or use the Live Server extension in VS Code.

Features:

Sliders for scale, rotation angle, and translation (x and y)
Reflection checkbox
Choice of triangle, square, or arrow shape
Live graph, transformation matrix, and coordinate table
Similarity check showing equal side ratios and preserved angles
Works on phones and computers, in light and dark mode
Deployment

The web app is a single static file, so it can be hosted for free.

Vercel

Upload index.html to a GitHub repository.
On vercel.com, click Add New → Project and import the repository.
Click Deploy.

GitHub Pages

Push the project to GitHub.
Go to Settings → Pages, choose the main branch and / (root) folder, and save.

Netlify Drag the project folder onto app.netlify.com/drop.

Applications
Computer graphics and game design
Image processing and computer vision
Maps, CAD, and robotics
Technologies Used
Python, NumPy, Matplotlib
HTML, CSS, JavaScript (SVG for the graph)
Author

Sejal Welekar
