---
layout: post
title: Raspberry PI as a FM transmitter 
date: 2013-03-26 20:28
author: funvill
comments: true
categories: [c, fm, Raspberry PI, RaspberryPI, transmitter]
---
<img class="alignright size-medium wp-image-3216" alt="pi_fm_gpio" src="http://www.abluestar.com/blog/wp-content/uploads/2013/03/pi_fm_gpio-300x225.jpg" width="300" height="225" />

A few weeks ago I found this tutorial on make magazine <a href="http://www.icrobotics.co.uk/wiki/index.php/Turning_the_Raspberry_Pi_Into_an_FM_Transmitter">Turning the Raspberry Pi Into an FM Transmitter</a>Â byÂ <a href="http://blog.codeclub.org.uk/blog/brief/">Code Club pihack</a>.

It uses the hardware on the raspberry pi that is actually meant to generate spread-spectrum clock signals on the GPIO pins to output FM Radio energy. This means that all you need to do to turn the Raspberry-Pi into a (ridiculously powerful) FM Transmitter is to plug in a wire as the antenna (as little as 20cm will do) into GPIO pin 4 and run the code posted below.

<strong>InstructionsÂ </strong>
<ol>
	<li>SFTP theÂ <em>pifm.c</em> andÂ <em>sound.wav</em>Â files on to your Raspberry PI.
<ul>
	<li>You will need to enable SHH to SFTP a file on your Raspberry PI</li>
</ul>
</li>
	<li>From the SHH terminal window, compile the pifm.c for your distro of linux.Â By defaultÂ <em>gcc</em>Â will produce aÂ <em>a.out</em>Â file as the compiled program.
<pre>gcc -lm -std=c99 pifm.c</pre>
</li>
	<li>Run the output. You must run the application as anÂ administrator (sudo) because thisÂ applicationÂ uses direct memoryÂ managementÂ to access the GPIO pins.
<pre>sudo ./a.out sound.wav</pre>
</li>
</ol>