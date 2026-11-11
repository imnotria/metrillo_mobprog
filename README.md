# metrillo_mobprog

Laboratory Discussion

1. What challenges did you encounter while installing or configuring Flutter?
Setting up the Flutter development environment presented a couple of notable hurdles regarding tool dependencies and path compatibility. Initially, the environment lacked the required Android SDK Command-line Tools component, which prevented Flutter from properly interfacing with the Android toolchain. Furthermore, the default installation directory for the Android SDK—located within the Windows user profile path—contained a space in the folder name. Because low-level Android NDK tools and compilers do not support spaces in their directory paths, this created a critical block for building Android applications.

2. Did you encounter any errors when running flutter doctor?
Yes, running flutter doctor successfully pinpointed these environment misconfigurations by flagging issues within the Android toolchain category. Specifically, it reported that the cmdline-tools component is missing and warned that the Android SDK location currently contains spaces, which is not supported by the Android SDK as it causes problems with NDK tools. These diagnostic messages were essential in isolating the exact causes of the build failures.

3. How did you resolve installation, dependency, SDK, or device-related issues?
Resolving these issues required a methodical approach to tool management and path restructuring. First, I accessed Android Studio’s SDK Manager to download and install the missing Android SDK Command-line Tools. Next, to fix the path issue, I created a clean, space-free directory at C:\Android\sdk and relocated the entire contents of the SDK from the old AppData folder into this new path. Afterward, I updated Flutter's internal configuration by executing the command flutter config --android-sdk "C:\Android\sdk" via PowerShell.

4. What did you learn about configuring a Flutter development environment?
Configuring a Flutter development environment taught me that mobile app development relies heavily on the seamless integration of multiple external toolchains, including the Flutter SDK, Android SDK, build tools, and platform compilers. Crucially, I learned that development environments can be surprisingly sensitive to minor file system details, such as whitespace in user profile directories. Understanding how these tools communicate and where they expect their dependencies to live is just as important as writing the application code itself.

5. What practices will you follow to make future Flutter development easier?
I will adopt several best practices to streamline future development work. I will consistently install software development kits and dependencies in clean, root-level, space-free directories right from the start to prevent path-related bugs. I will also make running flutter doctor a standard routine after any system or framework updates to catch missing components or configuration drifts early, ensuring a smooth and frustration-free workflow.