Mill-Clamp is a CNC programming utility that creates a CNC program which can be used to machine a clamp for milling workholding applications. The output CNC program can be interpreted by a 3-axis CNC machine running [GRBL](https://github.com/grbl/grbl), and the toolpath can be visually previewed at [Q'n'dirty toolpath simulator](https://nraynaud.github.io/webgcode/).

The generated program only controls feed motions and feedrate speeds. Other control-specific parameters, such as spindle speed, coolant control, tool numbers, etc. will have to be manually added to this program before running it in the CNC machine.

Here is a preview image of a toolpath generated by Mill-Clamp. The view is from a diagonal perspective to the flat surface of the material stock. Feed motions are represented with white lines. Rapid motions are represented with red lines.
![Toolpath Preview](/img/Toolpath-Preview.png)

Here is an image of a setup for machining a clamp. The outer profile of the clamp is being machined, and the slot and height adjustment hole have already been machined. 3 smaller clamps on the right are fixturing the workpiece to the workholding table.
![Use Case](/img/Use-Case.png)

In order to run this sofware and generate a CNC program, you must first be able to navigate your computer's file directory and execute commands from a console, and you must have Ruby 2.0.0 installed. Other Ruby versions will probably work as well.

To run the software, first download the .zip file and extract the contents to a directory of your choice. Then, access the ./bin directory from your console and execute:

```bash
ruby Mill-Clamp.rb
```

You will be prompted for several inputs. Press Enter after entering the desired value.

Here is an example of a console session for generating the CNC program:

```bash
ruby Mill-Clamp.rb
```

Units are inches.  

What is the length of the clamp?  
   3.0  

What is the width of the clamp?  
   1.5  

What is the thickness of the material stock?  
   0.5  

What is the XY end-milling feedrate?  
   15.0  

What is the Z plunge feedrate?  
   10.0  

What is the axial depth of cut?  
   0.15  

When setting up the CNC milling machine, follow these instructions: Use a 1/8" ball end mill as the cutting tool. Set X=0 and Y=0 on the workpiece such that the Cartesian quadrant within X>0 and Y>0 is solid workpiece material. Ensure that no point on the top of the workpiece surface extends more than 1/8" above Z=0. When running the CNC program, start with the tool at X=0, Y=0, and Z=0.

Here is your CNC program: (Edit this to add spindle speed, coolant control, tool numbers, etc. as necessary)

   G91  
   G0Z0.125  
   G90  
   G0X0.75Y2.25  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1X0.813F15.0  
   G3X0.813Y2.25I-0.063J0.0F15.0  
   G1X0.65F15.0  
   G3X0.65Y2.25I0.1J0.0F15.0  
   G91  
   G0Z0.125  
   G90  
   G0X0.75Y2.25  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1X0.813F15.0  
   G3X0.813Y2.25I-0.063J0.0F15.0  
   G1X0.65F15.0  
   G3X0.65Y2.25I0.1J0.0F15.0  
   G91  
   G0Z0.125  
   G90  
   G0X0.75Y2.25  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1X0.813F15.0  
   G3X0.813Y2.25I-0.063J0.0F15.0  
   G1X0.65F15.0  
   G3X0.65Y2.25I0.1J0.0F15.0  
   G91  
   G0Z0.125  
   G90  
   G0X0.75Y2.25  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1X0.813F15.0  
   G3X0.813Y2.25I-0.063J0.0F15.0  
   G1X0.65F15.0  
   G3X0.65Y2.25I0.1J0.0F15.0  
   G91  
   G0Z0.125  
   G90  
   G0X0.75Y2.25  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1X0.813F15.0  
   G3X0.813Y2.25I-0.063J0.0F15.0  
   G1X0.65F15.0  
   G3X0.65Y2.25I0.1J0.0F15.0  
   G0Z0.0  
   G91  
   G0Z0.125  
   G90  
   G0X0.75Y1.75  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1Y0.5F15.0  
   G1X0.788F15.0  
   G1Y1.75F15.0  
   G3X0.713I-0.038J0.0F15.0  
   G1Y0.5F15.0  
   G3X0.788I0.038F15.0  
   G91  
   G0Z0.125  
   G90  
   G0X0.75Y1.75  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1Y0.5F15.0  
   G1X0.788F15.0  
   G1Y1.75F15.0  
   G3X0.713I-0.038J0.0F15.0  
   G1Y0.5F15.0  
   G3X0.788I0.038F15.0  
   G91  
   G0Z0.125  
   G90  
   G0X0.75Y1.75  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1Y0.5F15.0  
   G1X0.788F15.0  
   G1Y1.75F15.0  
   G3X0.713I-0.038J0.0F15.0  
   G1Y0.5F15.0  
   G3X0.788I0.038F15.0  
   G91  
   G0Z0.125  
   G90  
   G0X0.75Y1.75  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1Y0.5F15.0  
   G1X0.788F15.0  
   G1Y1.75F15.0  
   G3X0.713I-0.038J0.0F15.0  
   G1Y0.5F15.0  
   G3X0.788I0.038F15.0  
   G91  
   G0Z0.125  
   G90  
   G0X0.75Y1.75  
   G91  
   G0Z-0.063  
   G1Z-0.213F10.0  
   G90  
   G1Y0.5F15.0  
   G1X0.788F15.0  
   G1Y1.75F15.0  
   G3X0.713I-0.038J0.0F15.0  
   G1Y0.5F15.0  
   G3X0.788I0.038F15.0  
   G0Z0.0  
   G91  
   G0Z0.125  
   G90  
   G0X1.563Y0.375  
   G91  
   G0Z-0.063  
   G1Z-0.063F10.0  
   G91  
   G1Z-0.15F10.0  
   G90  
   G2X1.125Y-0.063I-0.438J0.0F15.0  
   G1X0.375F15.0  
   G2X-0.063Y0.375I0.0J0.438F15.0  
   G1Y2.25F15.0  
   G2X1.563Y2.25I0.813J0.0F15.0  
   G1X1.563Y0.375F15.0  
   G91  
   G1Z-0.15F10.0  
   G90  
   G2X1.125Y-0.063I-0.438J0.0F15.0  
   G1X0.375F15.0  
   G2X-0.063Y0.375I0.0J0.438F15.0  
   G1Y2.25F15.0  
   G2X1.563Y2.25I0.813J0.0F15.0  
   G1X1.563Y0.375F15.0  
   G91  
   G1Z-0.15F10.0  
   G90  
   G2X1.125Y-0.063I-0.438J0.0F15.0  
   G1X0.375F15.0  
   G2X-0.063Y0.375I0.0J0.438F15.0  
   G1Y2.25F15.0  
   G2X1.563Y2.25I0.813J0.0F15.0  
   G1X1.563Y0.375F15.0  
   G91  
   G1Z-0.15F10.0  
   G90  
   G2X1.125Y-0.063I-0.438J0.0F15.0  
   G1X0.375F15.0  
   G2X-0.063Y0.375I0.0J0.438F15.0  
   G1Y2.25F15.0  
   G2X1.563Y2.25I0.813J0.0F15.0  
   G1X1.563Y0.375F15.0  
   G91  
   G1Z-0.15F10.0  
   G90  
   G2X1.125Y-0.063I-0.438J0.0F15.0  
   G1X0.375F15.0  
   G2X-0.063Y0.375I0.0J0.438F15.0  
   G1Y2.25F15.0  
   G2X1.563Y2.25I0.813J0.0F15.0  
   G1X1.563Y0.375F15.0  
   G0Z0.125  
   G0X0.0Y0.0  
   G1Z0.0  
   
This application was authored by Nick Edwards in 2015-2016. To contribute to this code base, create a pull request to https://github.com/edwardsCNC/Mill-Clamp