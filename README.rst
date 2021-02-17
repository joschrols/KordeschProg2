============================
Kordesch Program Information
============================
:Author: Joshua Olson <joschrfraols@gmail.com>
:Date: $Date: 2021-02-16 03:06:45 +0100 (Mi, 16. Feb 2021) $
:Version: 1.2
:Description: This is a program that combines features of Fityk v1.3.1 and Fiji's ImageJ2 into a single GUI application.

.. contents:: Overview

Installation
============
This application was packaged using PyInstaller 4.1. See the |PyInstaller|_ for more info.

.. |PyInstaller| replace:: PyInstaller manual
.. _PyInstaller: https://pyinstaller.readthedocs.io/en/stable

How to Install
--------------
1. Download the zip folder titled "emissivityprog.zip".
2. Extract the files from the zip folder by right-clicking on the folder and selecting "Extract All".

.. NOTE:: **Do not move any files or subfolders out of the folder. Doing so will ruin the application and make it unable to run properly. Creating a shortcut to the application itself should still work.**

Required Dependencies for Your System
-------------------------------------
You should not need to install any dependencies in order to run this application. It was created with the sole purpose of being able to run on any system without installing any of its dependencies, which can be a very complicated and time-consuming process.

Required Dependencies for Debugging
-----------------------------------
- Python version 3.8 or later (download at https://www.python.org/downloads/)
- Anaconda Spyder environment (download at https://www.anaconda.com/products/individual)
- Tkinter (usually included in Anaconda)

Running the Application
=======================

How to Run
----------
1. Find the EXE file in the folder (or a shortcut to it).
2. Open the application by clicking on the file.
3. A command prompt window will open. Here, the modules, packages, and binary files being implemented by the application will be displayed as they load. Once all of them have been loaded, the command window will close, and the application will open.

Troubleshooting
---------------
If the application does not open successfully using the method above, open the file using Windows Command Prompt as follows:

1. Open a Command Prompt window (press Windows key + R, then type "cmd" and click "OK" to open Command Prompt. Alternatively, you can search for Command Prompt in the Start menu).
2. Navigate to the application folder using ``cd <DIRECTORY/FOLDER NAME>``. See |thismanual|_ for help.
3. Type in the name of the application with the format extension included ("emissivityprog.exe") and hit Enter.
4. If issues persist, contact me.

.. |thismanual| replace:: this manual
.. _thismanual: https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/cd

How to Use
==========
The following details how to use each tool and command in the application.

Tools
-----

+----------------------------------+-------------+------------------------------------------------------+
| Icon                             | Tool        | Description                                          |
+==================================+=============+======================================================+
| .. image:: datas/icon-point.png  | point       | Click on a point in the image to draw a point.       |
|                                  |             | You can have multiple points drawn on the image      |
|                                  |             | simultaneously. Selecting “Analyze>>Measure”         |
|                                  |             | will measure all points drawn on the image.          |
+----------------------------------+-------------+------------------------------------------------------+
| .. image:: datas/icon-line.png   | line        | Click and drag between two points to draw a          |
|                                  |             | line. You can only have one line drawn on the        |
|                                  |             | image at a time. Select “Edit>>Adjust>>Line Width”   |
|                                  |             | to change the width of the line.                     |
+----------------------------------+-------------+------------------------------------------------------+
| .. image:: datas/icon-rect.png   | rectangle   | Click and drag between two points to draw a          |
|                                  |             | rectangle. You can not use “Analyze>>Measure” on     |
|                                  |             | rectangles. Rectangles are primarily used to crop    |
|                                  |             | images.                                              |
+----------------------------------+-------------+------------------------------------------------------+

Menu Commands
-------------
	.. list-table:: File Menu Commands
	   :widths: auto
	   :header-rows: 1

	   * - Command
	     - Keyboard Shortcut
	     - Operation
	   * - Open...
	     - Ctrl + O
	     - Select an image to open. Image must be a PNG or JPEG.
	   * - Save
	     - Ctrl + S
	     - Saves all changes made to the image.
	   * - Save As...
	     - --
	     - Opens a "Save File As" dialog.
	   * - Exit
	     - Ctrl + Q
	     - Closes the application

	.. list-table:: Edit Menu Commands
	   :widths: auto
	   :header-rows: 1
   
	   * - Command
	     - Keyboard Shortcut
	     - Operation
	   * - Cut
	     - --
	     - Disabled.
	   * - Copy
	     - --
	     - Disabled.
	   * - Paste
	     - --
	     - Disabled.
	   * - Clear
	     - Ctrl + F
	     - Clears all drawn elements from the canvas.
	   * - Line Width (in "Adjust" Menu)
	     - --
	     - Adjust the width of lines drawn with the line drawing tool.

	.. list-table:: Image Menu Commands
	   :widths: auto
	   :header-rows: 1
   
	   * - Command
	     - Operation
	   * - Crop
	     - Crops the image to a rectangle drawn on the canvas. [1]_
	   * - Set Scale
	     - Sets the scale of the image to a certain measurement and unit defined by the user. The user can draw a line on a section of the image and set the scale of the image using that line.
	   * - Rotate
	     - Disabled.

	.. list-table:: Analyze Menu Commands
	   :widths: auto
	   :header-rows: 1
   
	   * - Command
	     - Operation
	   * - Measure
	     - Displays the pixel coordinates, mean, min, and max pixel intensities, and other relevant information about the image at a drawn element's location. All data are displayed in a table that can be exported as a CSV.
	   * - Automatic (Computer Generated) Profile
	     - Identifies the bright spots in the image, and plots the intensity profiles along each row and column of spots. This plot can be manipulated and exported.
	   * - Manual Profile
	     - Plots the intensity profile of the image along a line drawn on the canvas. If no line is drawn, the profile of the entire image is plotted. This plot can be manipulated and exported.
	   * - Generate Voronoi Diagram
	     - Generates a Voronoi diagram of the image. For the best results, crop the image so that only the bright spots are visible.

.. NOTE:: The "Help" menu currently has no use.

Plot Commands
-------------
	.. list-table:: File Menu Commands
	   :widths: auto
	   :header-rows: 1
   
	   * - Command
	     - Operation
	   * - Save As Image...
	     - Saves the plot as an image.
	   * - Reset
	     - Resets the plot to its original layout

	.. list-table:: Data Menu Commands
	   :widths: auto
	   :header-rows: 1
   
	   * - Command
	     - Operation
	   * - Export As...
	     - Export the data as a CSV or text file.
	   * - Table
	     - Displays the data in a table. [2]_
	   * - Add Baseline
	     - Generates a baseline from the data.
	   * - Clear Baseline
	     - Clears the baseline from the plot.
	   * - Subtract Baseline
	     - Subtracts the baseline from the data.

	.. list-table:: Fit Menu Commands
	   :widths: auto
	   :header-rows: 1
   
	   * - Command
	     - Operation
	   * - Guess Peak
	     - Generates Gaussian fits for each apparent peak in the data, and then fits the entire dataset using a Levenberg-Marquardt algorithm.
	   * - Export Peak Parameters
	     - Exports the parameters of each peak as a CSV or text file.

License
=======
MIT |copy| 2021, Joshua Olson

.. |copy| unicode:: U+000A9 .. COPYRIGHT SIGN

.. [1] A rectangle must be drawn on the canvas for this to work.
.. [2] Table currently can't be scrolled through.
