1 源码部署appium服务的步骤:
	1 从https://github.com/Goldwind26464/appium下载分支branchV1.8.0
	2 在appium目录下运行下面的npm命令(使用淘宝源)
		npm install -g mocha
		npm install -g gulp
		npm install -g gulp
		npm install -g appium-doctor && appium-doctor --dev
		npm install
		gulp transpile
	3 手动替换以下文件(源:https://github.com/Goldwind26464/appium-uiautomator2-driver branchV1.12.0分支)
		目标:appium/node_modules/appium-uiautomator2-driver/package.json
		目标:appium/node_modules/appium-uiautomator2-driver/lib/driver.js
		目标:appium/node_modules/appium-uiautomator2-driver/lib/uiautomator2.js
	4 在appium/node_modules/appium-uiautomator2-driver目录中运行如下命令
		npm install
	5 下载https://github.com/Goldwind26464/appium-uiautomator2-server的分支branchV1.5.0
		在appium-uiautomator2-server目录下运行 gradle clean assembleServerDebug assembleServerDebugAndroidTest
	6 手动替换apk文件(源:appium-uiautomator2-server/app/build/outputs/apk目录下的两个apk文件)
		目标:appium/node_modules/appium-uiautomator2-driver/node_modules/appium-uiautomator2-server/apks目录下的两个apk
	7 在appium目录下运行 node . -a localhost -b 4729 -bp 4929 (注意 ip换成自己的appium服务器的ip,端口写对应手机设备的端口)