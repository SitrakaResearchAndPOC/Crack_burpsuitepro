# Crack_burpsuitepro
```
xhost +
```

```
docker run -tid --privileged -v /dev/bus/usb:/dev/bus/usb -v /tmp/.X11-unix:/tmp/.X11-unix:ro -v $XAUTHORITY:/home/user/.Xauthority:ro --net=host --env="DISPLAY=$DISPLAY" --env="LC_ALL=C.UTF-8" --env="LANG=C.UTF-8" --name crack_burpsuitepro -h crack_burpsuitepro kalilinux/kali-rolling
```
```
docker exec -it crack_burpsuitepro bash
```
```
apt update & apt install firefox-esr
```
```
apt install git axel  openjdk-21-jdk -y
```
Pour choisir manuellement si il y a plusieurs openjdk
```
update-alternatives --config java
```
```
git clone https://github.com/SitrakaResearchAndPOC/fork_Burpsuite-Professional-2025.git
```
```
cd fork_Burpsuite-Professional-2025/
```
```
echo "Downloading Burp Suite Professional Latest..."
```
```
version=2025
```
```
url="https://portswigger.net/burp/releases/download?product=pro&type=Jar"
```
```
axel "$url" -o "burpsuite_pro_v$version.jar"
```
# Execute Key Generator
```
echo "Starting Key loader.jar..."
```
```
(java -jar loader.jar) &
```
# Execute Burpsuite Professional
```
echo "Executing Burpsuite Professional..."
```
```
echo "java --add-opens=java.desktop/javax.swing=ALL-UNNAMED --add-opens=java.base/java.lang=ALL-UNNAMED --add-opens=java.base/jdk.internal.org.objectweb.asm=ALL-UNNAMED --add-opens=java.base/jdk.internal.org.objectweb.asm.tree=ALL-UNNAMED --add-opens=java.base/jdk.internal.org.objectweb.asm.Opcodes=ALL-UNNAMED -javaagent:$(pwd)/loader.jar -noverify -jar $(pwd)/burpsuite_pro_v$version.jar &" > burpsuitepro
```
```
chmod +x burpsuitepro
```
```
cp burpsuitepro /bin/burpsuitepro
```
