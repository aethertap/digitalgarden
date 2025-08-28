---
{"dg-publish":true,"permalink":"/projects/school-25-26/engineering/projects/microscope-camera/"}
---


# Camera for our Microscope

We will use a RaspberriPi 4B with an ArduCAM 3 fixed focus 75$\degree$ FoV to create a digital microscope from our current model.

## Camera resources

- [ArduCAM quick start guide](https://docs.arducam.com/Raspberry-Pi-Camera/Pivariety-Camera/Quick-Start-Guide/)
- [Rpi Cam GUI (github)](https://github.com/Gordon999/RPiCamGUI)
- [Some camera setup tips](http://www.microscopy-uk.org.uk/mag/indexmag.html?http://www.microscopy-uk.org.uk/mag/artfeb17/hw-RaspberryPi.html)
- [focus-stack](https://github.com/PetteriAimonen/focus-stack) is an open source tool to make a single sharp image from a large number of source images of the same target. Could be useful to do a low-framerate video while turning the focus knob, to get a full-depth all-in-focus picture.
- [simple design for side-illumination of top-down views](https://blog.noq2.net/cree-xhp50-as-a-diy-stereo-microscope-light-source.html)

## Full Auto

As a bonus project, we could use a [[grbl-software\|grbl-software]] controller connected with some small steppers to control the stage movement. If we combine that with the focus-stack software, it would be a great way to make high quality images, at least for non-moving targets. Motorizing lateral movement would also be incredibly useful.

If the kids learn Astro, we could connect the camera to a web app that allows the user to control the stage through the browser.

End game could be to use computer vision to tag a target, and have it keep that target in focus and in-frame despite movement.

## Lighting resources

The illuminator will be made from a CREE XLamp XHP35 on  a star-board. We will have to apply a heat sink and thermal glue, as well as a cooling fan. The brightness and (maybe) fan speed will be controllable through the RaspberryPi using PWM over a GPIO pin into a MOSFET power transistor.


# Mechanical Design

We will need designs for mounting the camera and the light source. The light source will need a duct for cooling air. The power supply will be from a plug-in wall adapter that outputs 12V DC.

A possible future direction might be to motorize the focus knobs to enable fully-automatic focus-stack images and remote operation from the web interface of the RasPI Cam GUI.

# Software

I would like to have a way to capture a focus-stack automatically. It should take a sequence of 10 or so photos in rapid succession, as the focus knob is slowly turned through the range of focus. Images should be output with the selected name, numbered, and then automatically fed into `focus-stack` to create the final output.

