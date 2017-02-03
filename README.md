#SETTING UP YOUR ECLIPSE EXPERIENCE(tm)
Because of github's file size limits, you need to download a 500MB Eclipse distro, and a 130MB toolchain - either from the links or https://drive.google.com/open?id=0B0jS3uE3U23qLW1UcnhyOUIxZG8. Everything else you may need to download has already been downloaded - these are all free to download tools elsewhere.

- First, we need Eclipse. Download the community edition of ds5 here (after registering) https://developer.arm.com/products/software-development-tools/ds-5-development-studio/editions/community-edition.

- We are now going to go get the version of the aarch64 toolchain that we want. We can find the toolchains here here: https://releases.linaro.org/components/toolchain/binaries/6.1-2016.08/aarch64-elf/

- Choose gcc-linaro-6.1.1-2016.08-i686-mingw32_aarch64-elf.tar.xz from the list and download that.

- Of course, this is compressed twice, but some versions of 7z have trouble with the xz extension. I have included xz.exe in the repository, which can be used via command line to unpack the toolchain as follows: xz -d (blah.tar.xz). xz.exe is located in the bin_ folders. If you have cygwin, then it has xz and you're good to go!

- Now you can use 7z to extract the toolchain tarball. A standalone version is included in this repo. Command line works, or you can use 7zFM.exe for a visual file explorer. They will accomplish the same thing: An extracted tarball that is now quite large.

- Extract ds5-ce-windows64-26rel2.zip then install Eclipse on your system via setup.exe.

- Start up Eclipse for DS5. It'll ask about workspace, just put it *somewhere*. This is where your project files will end up. Default in your working directory is probably fine.

- Start up the application: Eclipse for DS5. Set the workspace if you want, and when it loads, head to the 'window' tab at the top (second from the right) and select preferences at the bottom of the dropdown.

- Select DS5 from the left menu, then select toolchains.

- Add the GCC toolchain by navigating to inside the top-level bin file of the now extracted gcc-linaro tarball. If it insists it can't find it, curse repeatedly and then go download the mingw version. The version provided *should* work. Eclipse will restart.

- We should now have the toolchain in. Next, extract the Bare-metal_examples zip I have included. All the example zips can also be found in the DS5 eclipse folder in program files.

- Move the example calendar project from the into wherever you defined your workspace as previously, or right-click > import in the project explorer.

- Right-click on the project in the project explorer, and select `properties`. Then select C/C++ build. Uncheck `Display compatible toolchains only`, because we know best. Then select GCC6.1.1 to insist that yes, we're good to use it. Hit ok.

- Build the project from the Project dropdown menu at the top of eclipse, 4 from the right.

- Right-click on the project and select debug-as, then debug configuration (or do this through the run menu). Select DS-5 Debugger, select the calendar project (if nothing else is there, it should be selected already), and then Debug ARMv8-A and click debug.

- Congratulations, you are now debugging! It will send you to a debug view.
