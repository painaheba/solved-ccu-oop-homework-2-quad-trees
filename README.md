Download Link: https://assignmentchef.com/product/solved-ccu-oop-homework-2-quad-trees
<br>
<span class="kksr-muted">Rate this product</span>

HW #2 Quad Trees

Spatial Structures

<ul>

 <li>Computer graphics, image processing, and GIS (geographic information systems) all make use of a data structure called a quadtree.</li>

 <li>Quadtrees represent regional or block data efficiently and support efficient algorithms for operations like the union and intersection of images.</li>

 <li>A quadtree for a black and white image is constructed by successively dividing the image into four equal quadrants. If all the pixels in a quadrant are the same color (all black or all white) the division process for that quadtree stops.</li>

</ul>

HW #2 (2)

<ul>

 <li>Quadrants that contain both black and white pixels are subdivided into four equal quadrants and this process continues until each subquadrant consists of either all black or all white pixels. It is entirely possible that some subquadrants consist of a single pixel.</li>

 <li>For example, using 0 for white and 1 for black, the region on the left (see next slide) is represented by the matrix of zeros and ones in the middle. The matrix is divided into subquadrants as shown on the right where gray squares represent subquadrants that consist entirely of black pixels.</li>

</ul>

HW #2 (3)

HW #2 (4)

<ul>

 <li>A quadtree is constructed from the block structure of an image. The root of the tree represents the entire array of pixels.</li>

 <li>Each non-leaf node of a quadtree has four children, corresponding to the four subquadrants of the region represented by the node.</li>

 <li>Leaf nodes represent regions that consist of pixels of the same color and thus are not subdivided.</li>

 <li>For example, the image shown before, with the block structure on the right, is represented by the quadtree in the next slide.</li>

</ul>

HW #2 (5)

HW #2 (6)

<ul>

 <li>Leaf nodes are white if they correspond to a block of all white pixels, and black if they correspond to a block of all black pixels. In the tree, each leaf node is numbered corresponding to the block it represents in the diagram shown before.</li>

 <li>The branches of a non-leaf node are ordered from left-to-right as shown for the northwest, northeast, southwest, and southeast quanrants (or upper-left, upper-right, lower-left, lower-right).</li>

</ul>

HW #2 (7)

<ul>

 <li>A tree can be represented by a sequence of numbersrepresenting the root-to-leaf paths of black nodes.</li>

 <li>Each path is a base five number constructed by labeling branches with 1, 2, 3, or 4 with NW = 1, NE = 2, SW = 3, SE = 4, and with the least significant digit of the base, five number corresponding to the branch from the root.</li>

 <li>For example, the node labeled 4 has path NE, SW, which is 325 (base 5) or 1710 (base 10); the node labeled 12 has path SW, SE or 435 = 2310; and the node labeled 15 has path SE, SW, NW, or 1345 = 4410.</li>

</ul>

HW #2

<ul>

 <li>The entire tree is represented by the sequence of number (in base 10)<pre>     9 14 17 22 23 44 63 69 88 94 113</pre></li>

 <li>All images are black and white. All images are square and the size is a power of two, e.g., 4×4, 8×8, 16×16.</li>

 <li>Write a function (in C++,or Java if you prefer) that converts images into root-to-leaf paths and a function that converts root-to-leaf paths into images.</li>

</ul>

Input

HW #2

<ul>

 <li>The input contains one or more images. Each image is square, and the data for an image starts with an integer n, where |n| is the length of a side of the square (always a power of two, with |n| &lt; 64) followed by a representation of the image.</li>

 <li>A representation is either a sequence of n2 zeros and ones comprised of |n| lines of |n| digits per line, or the sequence of numbers that represent the root-to- leaf paths of each black node in the quadtree that represents the image.</li>

</ul>

HW #2

<ul>

 <li>If n is positive, the zero/one representation follows; if n is negative, the sequence of black node path numbers (in base 10) follows.</li>

 <li>The sequence is terminated by the number –1.</li>

 <li>A one-node tree that represents an all-black image is represented by the number 0. A one-node tree that represents an all-white image is represented by an empty sequence (no numbers).</li>

 <li>The end of data is signaled by a value of 0 for n.</li>

</ul>

HW #2 (11)

<ul>

 <li>For each image in the input, first output the number of the image, as shown in the sample output. Then output the alternate form of the image.</li>

 <li>If the image is represented by zeros and ones, the output consists of root-to-leaf paths of all black nodes in the quadtree that represents the image. The value should be based 10 representation of the base 5 path numbers, and the value should be printed in sorted order. If there are more than 12 black nodes, print a newline after every 12 nodes. The total number of black nodes should be printed after the path numbers.</li>

</ul>

Output

HW #2 (12)

• If the image is represented by the root-to-leaf paths of black nodes, the output consists of an ASCII

representation of the image with the character “.”

used for white/zero and the character “*” used for black/one. There should be n characters per line for an n x n image.

Sample Input

<pre>80000000000000000000011110000111100011111001111110011110000111000</pre>

HW #2 (13)

HW #2 (14)

-89 14 17 22 23 44 63 69 88 94 113 –1 20000-40 –10

HW #2 (15)

Output for the Sample Input

Image 19 14 17 22 23 44 63 69 88 94 113 Total number of black nodes = 11

Image 2 …….. …….. ….**** ….**** …***** ..****** ..****.. ..***…

HW #2 (16)

HW #2 (17)

Image 3Total number of black nodes = 0

Image 4 ************

****

Two last test images

<pre>80011000001111000110011001100110011111100110011001100110000000000</pre>