---
title: Final project overview and brainstorming guide
weight: 10
type: docs
---


# Introduction
You have gotten this far in ECE 385, well done. With the work you’ve done for the course so far, you have at least a beginner’s proficiency in System Verilog and working with an FPGA (Well hopefully at least). If I am being completely honest, even as a CA, the vast majority of the knowledge I earned from this class is from working on my final project. 
It is the best part of the class for some, and the worst part for some others. What you do is extremely open ended and you “choose your own adventure”. This is either your opportunity to show your truest creativity and ingenuity as a young engineer (and maybe salvage your grade with some high difficulty points) or for some people, an opportunity to coast by and take on an easier project. I highly recommend the former, even if you don’t “need it” for whatever grade you are going for. For a while, all you have to talk about in interviews is your class projects. If you do something zany or impressive enough, doing well on the ECE 385 final project could land you a nice job. If you want a nice job, coming up with an impressive final project could end up being extremely valuable to your career. 
Let’s split this up into a few sections, starting off with categorizing a few common types of final projects with their pros and cons. Next, will be some activities for coming up with a final project of your own.
Things to Keep in Mind While Brainstorming
- What are your interests?
- What could make this project the most useful and “enjoyable” for you?
- What is your engineering specialization? 

__________________________________________________________________________________________________________________________________________

# Pros and Cons of Common Projects

The most common projects that people do can be primarily grouped into three categories:
1. Video games
      - Description: You make a video game or emulate a system that plays ROMs, most of your time will be spent with video processing.
      - Difficulty point estimate: 2-8 (Hostless Emulation 9+)
      - Examples: Pacman(5), NES SoC clone(10), Tetris (
      - Pros:
         * Plenty of documentation out there 
         * You play video games
         * Additional coding experience in C embedded systems
      - Cons:
         * Often middling difficulty
         * Graphics are annoying to debug
         * It is basic.


2. Audio projects
      - Description: You store and play some sound. Most of your time will be spent debugging and understanding the SGTL5000 and DSP.
      - Difficulty point estimate: 6-10
      - Examples: Digital Synthesizer, Audio effects pedal, 
      - Pros:
         * Plenty of CAs out there to help 
         * You gain DSP knowledge
         * You use python for sampling and instantiation
      - Cons:
         * Oversaturation of audio CAs mean that difficulty points drop
         * One small issue takes hours to debug even with CA help


3. Advanced Embedded systems
      - Description: You make your FPGA communicate with another computing system. You probably could combine it with an audio or video game. A lot of things can go wrong with adding additional I/O to a project.
      - Difficulty point estimate: 0 (doesn’t work) or more than 8
      - Examples:  NES SoC clone(10), encoding/encryption, graphics acceleration
      - Pros: 
         * You do actual engineering
         * You get practice reading a lot of external documentation
         * You break the confines of the evil eclipse and Quartus
      - Cons
         * Hard and will take up a lot of time
         * May be difficult to articulate what exactly you want to do
         * May be difficult to find resources
__________________________________________________________________________________________________________________________________________

# Brainstorming your ideas quiz

Ratings are 1-5 low to high.
1. Are you interested in signal processing as a career? 
2. How comfortable are you with debugging and troubleshooting code?
3. How important is it to you to have a final project that stands out?
4. Are you interested in hardware design or software development?
5. How difficult was lab 7 and dealing with the VGA format for you?








If the rating of questions number one and five were more than 4, you should definitely do an audio project. 


If the rating you gave in number two plus the rating you gave in number three is less than 5, I suggest against an embedded systems project.


If VGA was easy for you and you’re interested in signal processing, consider a video processing project. 


__________________________________________________________________________________________________________________________________________
# Weird Things you can do with FPGA

Here are some of the more undisclosed options you can work with for your final project.


## JTAG_UART Connection with Python:

If you don’t like Eclipse, the good news is that you can avoid it entirely by using JTAG_UART connections using the following Python library.
https://github.com/tomverbeure/intel_jtag_uart
With this, you can write to SDRAM, have a constant bitstream between your computer and the FPGA, or even tell your computer to shut itself off (“os(‘shutdown /s -t 0’)” if you’re on windows). You have to instantiate SV files for taking in and out data, but using a shift register with it is simple enough. Once you have this though, you’ve essentially turned your FPGA into a raspberry pi. You can send data back and forth with  it as well.
## Real time video processing
Hey kid, you ever heard of CAMIF protocols? I thought not. It’s not the kind of project Zuofu would tell you. CAMIF is a standard for camera interfacing. You interface with a camera. There are a few options with this. You either need to have digital cameras around or you need to buy a usb webcam. The cheaper option is sending over images from a laptop via your JTAG cable. They can take in a constant stream and you can edit it on your FPGA and then send it back to the host computer.
Cell-Phone Motion Controls
My final project was one where I made a motion controlled digital synthesizer. Below is a link to the python end. I removed the parts where it communicates with the FPGA and all systemVerilog, but you could pretty easily connect it using the JTAG_UART library and ascii codes.
https://github.com/messes2/anyvideogamemotioncontrol




## Programming an FPGA with an FPGA

In theory, you could plug an FPGA into a secondary FPGA running off of a .pof file instead of a .sof file and you can have it communicate with a primary FPGA by storing the data into the SDRAM of the primary FPGA as a communication buffer between the two.




## Take Advantage of the Arduino Pinout

Keep in mind that anything you can do with an Arduino, you can do with an FPGA. If need be, don’t be scared to take off the DE-10 lite shield. You can run a 3D printer off of an FPGA, and thus, you will need to plug in and out controls for stepper motors.
