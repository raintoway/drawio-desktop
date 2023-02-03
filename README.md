Summary
-------
based on [drawio-desktop](https://github.com/jgraph/drawio-desktop)，link to this [issue](https://github.com/jgraph/drawio/issues/213).

this project adds the Animation for presentation sliders which is more useful in presentation.

just like this：

show/hide the ppt sideBar by type `alt + q`

![录制_2023_02_03_14_22_05_58](https://user-images.githubusercontent.com/38103330/216527515-17ac41b3-0a8d-40c4-be16-6d5b08db3d89.gif)

you can experience this function in [web](http://43.138.251.145:2335/drawio-desktop/drawio/src/main/webapp/index.html?dev=1&sync=manual) or download [win](http://43.138.251.145:2335/drawio-desktop/dist/win-unpacked/draw.io.exe).

Developing
----------

**draw.io** is a git submodule of **drawio-desktop**. To get both you need to clone recursively:

`git clone --recursive https://github.com/jgraph/drawio-desktop.git`

To run this:
1. `npm install` (in the root directory of this repo)
2. `npm install` (in the drawio directory of this repo `drawio/src/main/webapp`)
3. export DRAWIO_ENV=dev if you want to develop/debug in dev mode.
4. `npm start` _in the root directory of this repo_ runs the app. For debugging, use `npm start --enable-logging`.

To release:
1. Update the draw.io sub-module and push the change. Add version tag before pushing to origin.
2. Wait for the builds to complete (https://travis-ci.org/jgraph/drawio-desktop and https://ci.appveyor.com/project/davidjgraph/drawio-desktop)
3. Go to https://github.com/jgraph/drawio-desktop/releases, edit the preview release.
4. Download the windows exe and windows portable, sign them using `signtool sign /a /tr http://rfc3161timestamp.globalsign.com/advanced /td SHA256 c:/path/to/your/file.exe`
5. Re-upload signed file as `draw.io-windows-installer-x.y.z.exe` and `draw.io-windows-no-installer-x.y.z.exe`
6. Add release notes
7. Publish release

*Note*: In Windows release, when using both x64 and is32 as arch, the result is one big file with both archs. This is why we split them.

Local Storage and Session Storage is stored in the AppData folder:

- macOS: `~/Library/Application Support/draw.io`
- Windows: `C:\Users\<USER-NAME>\AppData\Roaming\draw.io\`


We are grateful for community involvement, bug reports, & feature requests. We do
not wish to come off as anything but welcoming, however, we've
made the decision to keep this project closed to contributions for 
the long term viability of the project.
