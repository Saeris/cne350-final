# Running Home Assistant on a Raspberry Pi

This is a brief overview of the steps needed to setup [HomeAssistant](https://www.home-assistant.io/) on a RaspberryPi and configuring it to use the [HomeAssistant Community Store (HACS)](https://hacs.xyz/)addon marketplace.

## What is Home Assistant?

Home Assistant is a headless Linux Operating System which runs a web service on your home network providing you with an interface to manage all of the smart devices within your home.

Where some devices are designed to work within a specific ecosystem like Apple's HomeKit or Samsung's SmartThings, this can be restrictive in that it narrows the range of products you can buy and the devices on which you can control and automate them.

With Home Assistant, you can manage and automate devices of many different ecosystems all from a singular, cross-platform interface in which you have complete control to customize and extend.

As an open-source project, a large community has developed around Home Assistant to extend it with new functionality. To make it easier to use these third-party tools, the Home Assistant Community Store (HACS) is one such extension you can install.

## Pre-Requisites

First of all, if you want to install Home Assistant on a RaspberryPi, you will need a model 4 or 5 (older models may not meet the minimum hardware requirements). Instructions for alternate installation methods can all be found [here](https://www.home-assistant.io/installation/).

Your Pi should be connected to your home network via ethernet to start with. Once initial setup is complete, you can configure Home Assistant to use your WiFi network instead.

## Installation

From there, you can follow along with their [DIY Guide](https://www.home-assistant.io/installation/raspberrypi) which simply walks you through how to use the [Official RaspberryPi OS Imager](https://www.raspberrypi.com/software/) to flash a MicroSD Card with the Home Assistant OS.

With the MicroSD Card successfully flashed, insert it into your Pi and connect it to power. Home Assistant will run through some first-time setup, at the end of which you will see a command line prompt and the Home Assistant logo displayed on screen. From this point you can access the Home Assistant dashboard from your browser on another computer by navigating to [http://homeassistant.local:8123](http://homeassistant.local:8123).

This will begin the [Onboarding Flow](https://www.home-assistant.io/getting-started/onboarding/) to configure your user account and some basic information about your home. At the end you will be presented with a list of compatible devices that were automatically detected on your home network.

## Add Visual Studio Code Addon

Before we can install HACS, we need to have a way to run CLI commands through Home Assistant's web interface. One way we can do this is by installing the [Studio Code Server addon](https://github.com/hassio-addons/addon-vscode/blob/main/vscode/DOCS.md), which will both let us edit files on our Pi with a familiar IDE and run shell commands via it's integrated terminal.

## Installing Home Assistant Community Store

Assuming you installed the Studio Code Server addon above, you can then open the web UI from the left-hand navigation and then open the terminal by pressing ``Ctrl + Shift \``` on your keyboard. In the terminal, you can now run the following:

```bash
wget -O - https://get.hacs.xyz | bash -
```

Let this script run, responding to any prompts that come up. When it completes, follow along with the [initial configuration guide](https://hacs.xyz/docs/configuration/basic) to compelte setup.

## What next?

You're now ready to customize the heck out of your Home Assistant server! You can check out this [getting started guide for HACS](https://hacs.xyz/docs/basic/getting_started) or take a look at some [dashboard themes](https://smarthomescene.com/blog/best-home-assistant-dashboard-themes-in-2023/) you can install. If you really want to dive deep, you can even build your own dashboard widgets using React with the help of [HAKit](https://github.com/shannonhochkins/ha-component-kit).
