# aohw25-Scalable-Mandelbrot-set-generator-project

I Included two .slx files for model composer

wholesystem_with_output_quadoutput.slx - Full system to be simulated
<br/>
stream_mdbrt_backup5.slx - Full system to be compiled for vivado

Default parameters for both .slx files in matlab are:

bits = 48<br/>
binpoint = 32<br/>
bitsiter = 12<br/>
bitswidth = 12<br/>
bitsheight = 12<br/>


<br/>
For simulating, specifically the topmost view of the mandelbrot set: <br/>
<br/>
InMaxIterations = 100<br/>
InMaxIterations = [1, 100]<br/>
InStartX = [1, -2]<br/>
InStart = [1, 1]<br/>
InStartX = [1, -2]<br/>
InStopX = [1,0.47]<br/>
InStartY = [1,-1.12]<br/>
InStopY = [1,1.12]<br/>

<br/>
<br/>
To get the resulting image in the Matlab environment:
step1 = horzcat(out.ITER.Data, out.VALID.Data)
step2 = step1(step1(:,2) == 1, :)
step3 = reshape(step2(:,1),101,101)
imagesc(step3')

<br/>
For running the Jupyter notebook, upload it, and the .bit and .hwh file to the same directory

When compiling the system in vivado, the S2MM_LENGTH register in the AXI DMA IP core needs to be set to ~14 bits for large images
