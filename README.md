# AutomationTestingSetup

Appium :

For Mac Setup :

Appium Setup :

1. Install Homebrew using below command :

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

2. Check brew is install successfully by using below command :
brew -v
bash: brew: command not found
/usr/bin/open ~/.bash_profile
bash-3.2$ /usr/bin/open ~/.bash_profile
bash-3.2$ source .bash_profile
echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
curl: (22) The requested URL returned error: 404
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/anishkumar/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
brew help
brew -v

3. Check node and npm is install. Use below command for check : 
node -v
bash: node: command not found
bash-3.2$ npm -v
bash: npm: command not found

4. Install node using beow command :
brew install node
which npm

5. Install appium without driver :
npm install -g appium
check appium is working by using below command :
 appium
 which appium
 
 6. Install java 15 or above 10 :
 From oracle :
 https://www.oracle.com/java/technologies/downloads/archive/
 Command : echo $SHELL
Display : /bin/zsh
Command : /usr/libexec/java_home
Display : /Library/Java/JavaVirtualMachines/jdk-15.0.2.jdk/Contents/Home
Command : ls -a
Create file .zshrc using vim : Command is : vim .zshrc
Add below line in .zshrc file and save
export JAVA_HOME=$(/usr/libexec/java_home)
export PATH="${JAVA_HOME}/bin:/usr/local/opt/node@14/bin:$PATH"
Command to check java home : echo $JAVA_HOME
Command to check path : echo $PATH

Setup for Android Drive and android simulator, sdk :

6. To get appium driver list use below command :
appium driver list
If you see any error and driver list not getting display then use below command :
npm install appium@next -g
appium driver list

7. Install uiautomator2 driver for android using below command :
appium driver install uiautomator2
appium driver list
 appium
 Control C to exit
 
8. Install Android Studios with intel chip which downloaded intel haxm :
Intel HAXM helps if you are running emulator, it will run smooth.
If android studios is already installed with using apple chip, then download intel haxm using below command :
 brew install intel-haxm
 And if above command throw below error :
 Error: Cask intel-haxm depends on hardware architecture being one of [{:type=>:intel, :bits=>64}], but you are running {:type=>:arm, :bits=>64}.
 Then uninstall the android studio and reinstall with intel chip.
For uninstall android studios below is the command :
 rm -Rf /Applications/Android\ Studio.app
rm -Rf ~/Library/Preferences/AndroidStudio*
rm -Rf ~/Library/Preferences/Google/AndroidStudio*
rm -Rf ~/Library/Preferences/com.google.android.*
rm -Rf ~/Library/Preferences/com.android.*
rm -Rf ~/Library/Application\ Support/AndroidStudio*
rm -Rf ~/Library/Application\ Support/Google/AndroidStudio*
rm -Rf ~/Library/Logs/AndroidStudio*
rm -Rf ~/Library/Logs/Google/AndroidStudio*
rm -Rf ~/Library/Caches/AndroidStudio*
rm -Rf ~/.AndroidStudio*
Use below link for reference :
https://www.geeksforgeeks.org/how-to-completely-uninstall-android-studio-on-mac/

9. Setup the ANDROID_HOME Environment variable :
Open vim using command :
cd ~/
open -e .zshrc

Add java home and android home environment varaiable :

export JAVA_HOME=$(/usr/libexec/java_home)
export ANDROID_HOME=${HOME}/Library/Android/sdk
export PATH="${ANDROID_HOME}/platform-tools:${ANDROID_HOME}/cmdline-tools:${JAVA_HOME}/bin:/usr/local/opt/node@14/bin:$PATH"

save it and close it.
Use below command to execute vim file :
cd ~/
source .zshrc
Then check the environment is present using below command :
echo $ANDROID_HOME
echo $PATH

10. Setup emulator for android device :
Open adv manager
create phone (piexel 5)
download image file, API 12

11. Set below desired capabilities inside appium inspector :
{
  "appium:automationName": "uiautomator2",
  "platformName": "Android",
  "appium:deviceName": "sdk_gphone64_arm_64",
  "appium:app": "./APKDemoTesting/ApiDemos-debug.apk"
}
start the appium server and session of appium session, and it will launch the apk.

12. In case of real device setup, install vysor for android.


