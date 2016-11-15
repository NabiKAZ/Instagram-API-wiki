### Technical information

**Navigation**

1. [Extracting Instagram's Signature Key](#extracting-instagrams-signature-key)
2. [Capturing the endpoints](#capturing-the-endpoints)

## Extracting Instagram's Signature Key

There is one thing required in order to make the API works, and that is the `IG_SIG_KEY`. In our case:

```php
const IG_SIG_KEY      = 'c1c7d84501d2f0df05c378f5efb9120909ecfb39dff5494aa361ec0deadb509a';
const SIG_KEY_VERSION = '4';
```

There are many ways to obtain this key:

### mokhdzanifaeq/arminject

Download: https://github.com/mokhdzanifaeq/arminject

![arminject](http://i.imgur.com/9TWSLlq.gif)

## Manually

**Source:** https://mokhdzanifaeq.github.io/2015/09/28/extracting-instagram-signature-key-2/

### WHAT IS GIKDBG?

gikdbg is a mobile assembly-level debugger for windows platform. the debugger is based on 3 main software:

- [OllyDbg](http://www.ollydbg.de/) (32-bit assembler level analysing debugger)
- [GDB](https://www.gnu.org/software/gdb/) (GNU project debugger)
- [LLVM](http://llvm.org/) (collection of modular and reusable compiler and toolchain technologies)

in order to begin working with gikdbg, we will need an android system running on ART runtime (android debugging enabled). then, connect your device to your computer and open gikdbg. starting gikdbg, we will be greeted with the following screen

![re1](http://i.imgur.com/4eSUL97.png)

Next step is to connect the debugger to our android system. this can be performed from the menu `ART Debug > Server > Device`. then choose your android system from the list. Double click on it and a dialog will appear, asking wherever to install the appropriate libs to your android sytem. click **Yes**

![re2](http://i.imgur.com/N0zUnvI.gif)

if everything went well, **ADB Shell** window will appear. now run the instagram app in your android system and attach the process to the debugger through the menu
`ART Debug > File > Attach`. next, select **com.instagram.android** from the process list and click on the **Attach** button and wait for it to load

![re3](http://i.imgur.com/oatSqm7.gif)

now we need to view the memory of the binary file where the signature key get called. this can be accomplished from the menu `ART Debug > View > Module`. search for **libstrings.so** in the list and double click on the module

![re4](http://i.imgur.com/zaq9Wch.gif)

scroll down and find the **strlen** function which is called before **crypto_auth_hmacsha256_init** function and set a breakpoint with `F2`. then run the app with `F9`

![re5](http://i.imgur.com/XcZ4pEB.png)

now when you login to instagram in your android device, the breakpoint will be hit. the only thing to do now is extracting the key from the memory. we can accomplished that by right clicking on the register memory address that hold the key (in this case it would be r0) and choose `Follow in dump` from the menu

![image2](http://i.imgur.com/Hj1oE5V.gif)

now when you login to instagram in your android device, the breakpoint will be hit. the only thing to do now is extracting the key from the memory. we can accomplished that by right clicking on the register memory address that hold the key (in this case it would be r0) and choose Follow in dump from the menu

## Capturing the endpoints

You will need a proxy, there are a lot, so use the one you prefer. You will find a lot of information in Google.