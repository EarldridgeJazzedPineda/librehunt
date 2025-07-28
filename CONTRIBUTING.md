# Adding a new Linux distribution to LibreHunt
First, [fork the LibreHunt repository on GitHub](https://github.com/aviwad/librehunt/fork) and then clone it using `git clone <url of your forked repository>`. Make sure you have Git installed.

Open the librehunt.js file in a text editor, and copy the following template entry:
```
   {
      "notrolling":0,
      "matches":[],
      "name":"",
      "lookalike":"",
      "popularity":0,
      "oldnew":0,
      "gaming":0,
      "shortdes":"",
      "touch":0,
      "desktops":"",
      "link":"",
      "linuxexpertise":0,
      "codename":"",
      "donate":"",
      "customtweaks":0,
      "freesoftware":0,
      "architecture":[],
      "sourcebased":0,
   }
```

to the end of the `distros` array, like this:
```
   ...
   },
   {
      "notrolling":0,
      "matches":[],
      "name":"",
      "lookalike":"",
      "popularity":0,
      "oldnew":0,
      "gaming":0,
      "shortdes":"",
      "touch":0,
      "desktops":"",
      "link":"",
      "linuxexpertise":0,
      "codename":"",
      "donate":"",
      "customtweaks":0,
      "freesoftware":0,
      "architecture":[],
      "sourcebased":0,
   }
]
```
Make sure to add a comma at the end of the previous entry.

Next, fill out the following properties with the appropriate value:
* `notrolling` - defines how often the distributions makes software updates and releases. Possible values are:
  * `0` - the distribution has a rolling release cycle, which means that software updates are made available in repositories as soon as possible
  * `1` - the distribution has a fixed release cycle, which means that new releases are made every once in a while with fixed versions of software.
* `name` - the official name of the distribution, including the words "Linux" and "OS" if any.
* `lookalike` - defines what the distribution's default desktop environment looks like. Possible values are:
  * `"mac"` - the default desktop environment resembles that of Apple's macOS 10.0 onwards. It features two bars, one at the top and one at the bottom of the screen. The top bar includes notification icons, date and time, and optionally the application menu bar. The bottom bar includes pinned applications. GNOME and Pantheon by default resemble macOS. 
  * `"windows"` - the default desktop environment resembles that of Microsoft Windows 95 onwards. It features a single bar at the bottom of a screen (commonly known as a "taskbar") that includes a start menu, pinned applications, notification icons, and date and time. KDE Plasma and Cinnamon by default resemble Windows.
  * `"0"` - the default desktop environment doesn't resemble macOS or Windows based on the above definitions, or the distribution doesn't come with a default desktop environment.
* `popularity` - defines how popular the distribution is within the Linux community. Possible values are:
  * `0` - the distribution is unpopular or niche. As a rule of thumb, if the distribution name + "linux" has less than 1,000,000 results on Google, then it is considered unpopular.
  * `1` - the distribution is popular and well-supported. As a rule of thumb, if the distribution name + "linux" has more than 1,000,000 results on Google, then it is considered popular.
* `oldnew` - defines how well the distribution performs on old hardware. Possible values are:
  * `0` - the distrubution works poorly on old hardware, or is not optimized for older hardware.
  * `1` - the distribution works well on old hardware, or is optimized for older hardware.
* `gaming` - defines how well the distribution can play games. Possible values are:
  * `0` - the distribution can play games but poorly, or doesn't support games at all.
  * `1` - the distribution can play games well, or is designed specifically for gaming purposes.
* `shortdes` - a short description of the distribution and/or its features, preferably a snippet of text from the distribution's official website.
* `touch` - defines whether or not touchscreen devices are supported by the distribution. Possible values are:
  * `0` - the distribution's kernel doesn't support touchscreen devices.
  * `1` - the distribution's kernel supports touchscreen devices, or the distribution allows you to set touchscreen support in the kernel configuration.
* `desktops` - a list of desktop environments officially supported by the distribution. The names "GNOME", "MATE", "LXQt", and "Xfce" are standardized.
* `link` - the URL of the distribution's official website.
* `linuxexpertise` - defines how easy or hard it is to install, configure, and use the distribution. Possible values are:
  * `0` - the distribution is for beginners. The ComputeFreely definition is:<br>
  "These are distributions that aim for the widest possible audience. Built for use as desktop operating systems, these tend to focus on ease of use and are often fairly straightforward to use and don't require much prior knowledge about Linux to get going."
  * `1` - the distribution is for intermediate users. The ComputeFreely definition is:<br>
  "If you have some familiarity with Linux systems these distributions are good jumping off points, but require a bit more work out-of-the-box to get set-up. Distributions in this category can be somewhat niche, come bundled with some more technical tools, or focus on a specific category of use."
  * `2` - the distribution is for advanced users. The ComputeFreely definition is:<br>
  "These are distributions that are very niche or specialized and require a lot of prior knowledge about things like package management, navigating a terminal and overall familiarity with Linux systems. It's here where you will find yourself doing a lot of the configuration yourself and tailoring your system to your needs or even building one from scratch."
* `codename` - a short name for the distribution that defines the name of the logo image. For example, if the codename is `gentoo`, then the logo image for that distribution is gentoo.png.
* `donate` - the URL of a page where can donate money or otherwise contribute to the distribution.
* `customtweaks` - defines whether or not the distribution's default desktop environment is heavily customized. Possible values are:
  * `0`: the default desktop environment uses the default settings, or is kept as close as possible to the default settings.
  * `1`: the default desktop environment is customized to the point it no longer resembles the default settings.
* `freesoftware` - defines whether or not the distribution uses only free software [as defined by the Free Software Foundation](https://www.gnu.org/distros/free-distros.en.html). Possible values are:
  * `0` - the distribution is not on the FSF's free GNU/Linux distributions list, and can include binary blobs or proprietary software preinstalled.
  * `1` - the distribution is on the FSF's free GNU/Linux distributions list and uses only free software as defined by them.
* `architecture` - the instruction set architectures (ISAs) supported by the distribution. Possible values are:
  * `"x86"` - the distribution supports the 32-bit x86 ISA created by Intel, also known as IA-32, i386, i486, i586, or i686.
  * `"other"` - the distribution supports ISAs other than x86 (32-bit or 64-bit), including but not limited to ARM, PowerPC, and RISC-V.
* `sourcebased` - defines how a users installs software in the distribution. Possible values are:
  * `0` - the distribution provides pre-built software, also known as "binary packages", in repositories from which they can be installed using a package manager.
  * `1` - the distribution has users build software from source code, whether or not using a package manager. Support for binary packages is optional.

Example entry:
```
   {
      "notrolling":1,
      "matches":[],
      "name":"Bodhi Linux",
      "lookalike":"0",
      "popularity":0,
      "oldnew":1,
      "gaming":0,
      "shortdes":"Lightweight, with its own in-house Enlightenment desktop, while being based on Ubuntu.",
      "touch":0,
      "desktops":"The Enlightenment Desktop",
      "link":"https://www.bodhilinux.com/",
      "linuxexpertise":1,
      "codename":"bodhi",
      "donate":"https://www.bodhilinux.com/donate/",
      "customtweaks":1,
      "freesoftware":0,
      "architecture":[],
      "sourcebased":0,
   }
```

Save the changes to librehunt.js. Use `git diff` to inspect your changes, and once you're happy with them, run:
```
git add librehunt.js
git commit -m "Add <name of distribution>"
git push
```
Make sure that your Git is configured with the proper credientials so that you can push the commit to your fork.

Finally, [create a pull request on the main LibreHunt repository](https://github.com/aviwad/librehunt/compare). Contributors with write access will review your pull request and merge it to the repository if it is good to go.