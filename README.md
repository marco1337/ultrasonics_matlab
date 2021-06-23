# Ultrasonics using Matlab

Hello to everyone! This repository contains my progress in ultrasonic study for my
master's thesis in Biomedical Engineering. I will try to put all the resources I use as I
go and also my opinion about them.
The purpose of this repository is to show a how someone with little knowledge in the field
goes about learning about Ultrasonics and also Matlab. There are not many resources for this,
and most of them are too academic and strict to follow, or are too casual and without any 
commentary about how some code is working and why is it correct. This repository will try to be 
the bridge between these two approaches: easy to understand at first, but with depth
when it is required.

# Installation and setup

I installed the k-wave toolbox from http://www.k-wave.org/index.php and it was really
easy. The only part that didn't work was seeing the examples in the help panel, but
it was no problem because I could browse to them in the k-wave folder I copied to the
Matlab directory (there may be problemas with permissions if the k-wave directory is in
a protected directory, but I only had to copy the files to another directory with the 
correct permissions)

# Examples from http://www.k-wave.org/documentation/k-wave.php

My first step to work with k-wave was to run some of the examples from the link 
above. To run the examples faster, I recommend installing the Parallel Computing Toolbox if you
have a PC with a graphics card because the speed up is big. However, some examples had trouble
running with the GPU option enabled, so I had to default to the simpler CPU only option.

Examples run:

## example_ipv_homogeneous_medium.m
No problem. Ran with CPU and GPU.
## example_us_defining_transducer.m
No problem when running with CPU. When running with the option DATA_CAST = 'gpuArray-single', this error appears:

    Error using set
    Value must be a numeric vector whose values increase.

    Error in stackedPlot (line 180)
        set(gca, 'YTick', yticks, 'YTickLabels', fliplr(y), 'YLim', ylims);

    Error in example_us_defining_transducer (line 201)
    stackedPlot(kgrid.t_array * 1e6, {'Sensor Position 1', 'Sensor Position 2', 'Sensor Position 3'}, sensor_data);



