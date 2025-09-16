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
Cracker :

Copier la license sur le crack keygen loader.jar puis cliquer sur "Run.." </br>
Choisir activation manuelle de burpsuitepro </br>
Coller la license  dans burpsuitepro</br>
Copier dans burpsuiteproo activation request puis coller sur request activation de keygen loader.jar </br>
Copier activation response de keygen loader.jar puis coller sur burpsuitepro pour activer </br>

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
# In new terminal (ctrl+shift+T)
```
docker commit -m "version 1" crack_burpsuitepro crack_burpsuitepro:v1.1
```
# Load and re-ru : 

```
xhost +
```
```
docker run -tid --privileged -v /dev/bus/usb:/dev/bus/usb -v /tmp/.X11-unix:/tmp/.X11-unix:ro -v $XAUTHORITY:/home/user/.Xauthority:ro --net=host --env="DISPLAY=$DISPLAY" --env="LC_ALL=C.UTF-8" --env="LANG=C.UTF-8" --name crack_burpsuitepro -h crack_burpsuitepro crack_burpsuitepro:v1.1
```
```
docker exec -it crack_burpsuitepro bash
```
```
burpsuitepro
```
