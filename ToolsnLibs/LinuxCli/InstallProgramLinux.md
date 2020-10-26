# Install Programs in Linux

> *Considered distro: PopOS19.10*

### **1.  Install Software in Ubuntu Using Software Center**

* * *

### **2. Install  Using .deb Files**

* * *

### **3. Install  Using Flatpak**

* * *

```shell
sudo apt install flatpak
```

### **4. Install Software in Ubuntu Using Snap Packages**

* * *

```shell
sudo apt install snapd

sudo snap install <package>
```

### **5. Install  Using AppImage**

* * *

### **6. Install  Using Apt Commands**

* * *

### **7\. How To Install App in Ubuntu Using PPA**

* * *

PPA – Personal Package Archive . Many developers want to offer the latest version of their software directly to the end users.

```shell
sudo add-apt-repository ppa:embrosyn/cinnamon
sudo apt update
sudo apt install cinnamon
```

- adding the PPA repository to system’s source list, 

- updating the cache of software list

- installing the specific software using PPA apt command.

### **8. Using Synaptic Package Manager**

* * *

### **9.  Install Using dpkg**

* * *

**Install a package**

```shell
sudo dpkg -i <filename>.deb
```

* **Resolve Dependency Errors**

```shell
sudo apt-get install -f
```

* **Remove the application**

```shell
dpkg -r <packagename>.deb
```

* **To Reconfigure/Repair the deb installation**

```shell
sudo dpkg-reconfigure packagename
```

### **10. Install  Using the Source Code**

* * *

### **11. Installing Packages via Web Browsers**

* * *

The [**APT protocol (or apturl)**](https://help.ubuntu.com/community/AptURL) is a simple and hassle-free way to [install software in Ubuntu Linux](https://www.ubuntupit.com/best-useful-ubuntu-software-will-make-productive/). 

![Synaptic package install using apturl](https://www.ubuntupit.com/wp-content/uploads/2018/06/Synaptic-package-install-using-apturl.png)

### **12\. Install Python Applications via Pip – “Pip Installs Packages”**

* * *
