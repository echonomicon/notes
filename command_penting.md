# manjaro

## remove unused package

    pacman -Qdt
    pacman -Scc

## update aur package

    trizen -Syua

## battery: status

    upower --dump

## bluetooth start service

    sudo systemctl start bluetooth

## bluetooth show configuration

    cat /etc/bluetooth/main.conf

## remote rdp

    xfreerdp /v:192.168.0.132 /u:skai

## setup ssh

    sudo pacman -S openssh
    sudo systemctl status sshd
    sudo nano /etc/ssh/sshd_config
    sudo systemctl enable sshd
    sudo systemctl start sshd
    ssh echo@192.168.43.251

# routing: add routing

    sudo ip route add xx.xx.xx.x/24 via 192.168.0.1 metric 100 dev wlp3s0
    sudo ip route add xx.xx.xx.x/24 via 192.168.0.1 dev wlp3s0
    ip route show

# nvidia: run nvidia graphic on manjaro

    sudo optirun -b none nvidia-settings -c :8
    dmesg | grep bbswitch
    glxgears -info
    sudo optirun glxgears -info
    sudo primusrun glxgears -info
    sudo primusrun steam steam://rungameid/570 -info

# github

## initial repository

    git init
    git add .
    git commit -m "Initial commit"
    git remote add origin youruser@yourserver.com:/path/to/my_project.git
    git push origin master

## clone repository

    git clone https://github.com/USERNAME/REPOSITORY_NAME.git

## reset local, ambil dari repository remote

    git reset --hard origin/master
    git pull

# flutter

## How to install flutter

### 1. install git

    winget install --id Git.Git -e --source winget

### 2. install flutter

    git clone https://github.com/flutter/flutter.git -b stable

### 3. update path

    D:\Development\flutter\bin

### 4. install android studio

    https://developer.android.com/studio#downloads

### 5. install text editor (visual studio code)

    https://code.visualstudio.com/download

### 6. flutter doctor

    flutter doctor
    flutter doctor --android-licenses

## flutter connect device

    adb tcpip 5555
    adb connect device_ip_address

## launch multiple device flutter

    flutter run -d all

## build app bundle for smaller size

    flutter build appbundle

## flutter web

    export CHROME_EXECUTABLE=/mnt/c/Program\ Files/Google/Chrome/Application/chrome.exe

    flutter build web
    cd build/web/
    python -m http.server 8000
    firebase deploy

## run relase mode

    flutter run --release
    flutter run --profile

# laravel: start in homestead

    vagrant up --provision
    vagrant ssh
    php -S 192.168.10.10:8000 -t public

# ngrok: start services

    ngrok http 192.168.10.10:8000 -host-header=saharga.dev

# docker

## start services

    sudo systemctl start docker

## remove file docker

    var/lib/docker
    docker system prune -a

# node js: run npm

    sudo npm start

# react-native

## create project

    npx react-native init ProjectName
    npm i @react-native-async-storage/async-storage
    npm i @react-native-community/clipboard
    npm i @react-native-firebase/app
    npm i @react-native-firebase/messaging
    npm i axios
    npm i @react-navigation/stack
    npm i @react-navigation/native
    npm i @react-navigation/bottom-tabs
    npm i geolib
    npm i react-native-camera
    npm i react-native-dotenv
    npm i react-native-flash-message
    npm i react-native-geolocation-service
    npm i react-native-svg
    npm i react-native-svg-transformer
    npm i react-native-tab-view
    npm i react-native-vector-icons
    npm i react-redux
    npm i redux
    npm i redux-thunk
    npm i rn-sliding-up-panel
    npm i watchman
    npm install react-native-reanimated react-native-gesture-handler react-native-screens react-native-safe-area-context @react-native-community/masked-view

## uninstall npm package on react native

    npm uninstall {package name} -save

## start project

    npm start
    npx react-native run-android

## react native clear project

    rm -rf node_modules
    npm cache clean --force
    npm install
    npm start -- --reset-cache

## build apk

    cd android
    ./gradlew clean
    ./gradlew assembleRelease
    ./gradlew bundleRelease

## additional setting

## watchman todo install

    typerscript error
        javasript.validate: disable
    add local.properties in android/gradle/wrapper
        sdk.dir = /home/echo/Android/Sdk
    edit gradle version in android/gradle/wrapper/gradle-wrapper.properties
        distributionUrl=https\://services.gradle.org/distributions/gradle-6.3-all.zip

# keychorn: k6 fix ubs fn keys

    echo 0 | sudo tee /sys/module/hid_apple/parameters/fnmode
    https://www.reddit.com/r/MechanicalKeyboards/comments/d5io49/keychron_k2_f_keys_dont_work_w_linux_help/

# ubuntu server

## access via ssh

    ssh username@192.168.xxx.xxx -p 22

## install ftp

    sudo apt install vsftpd
    sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.echo
    sudo nano /etc/vsftpd.conf
    write_enable=YES
    chroot_local_user=YES
    allow_writeable_chroot=YES
    sudo systemctl restart vsftpd
    sudo systemctl status vsftpd
    https://musaamin.web.id/cara-install-ftp-server-dengan-vsftpd-di-ubuntu/

## server log

    more /var/log/auth.log
    more /var/log/syslog
    sudo more vsftpd.log
    lastlog

## timezone set

    sudo dpkg-reconfigure tzdata
    sudo timedatectl set-timezone Asia/Jakarta

## snort

    https://snort-org-site.s3.amazonaws.com/production/document_files/files/000/000/251/original/Snort_3_on_Ubuntu.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIXACIED2SPMSC7GA%2F20201206%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20201206T045307Z&X-Amz-Expires=172800&X-Amz-SignedHeaders=host&X-Amz-Signature=3d72d8e802135201bf6988a02fadb99b30e89b92e855bcfe59d64c06732fad37

    mkdir ~/snort_src
    cd ~/snort_src
    sudo apt-get install -y build-essential autotools-dev libdumbnet-dev \
    libluajit-5.1-dev libpcap-dev zlib1g-dev pkg-config libhwloc-dev \
    cmake
    sudo apt-get install -y liblzma-dev openssl libssl-dev cpputest \
    libsqlite3-dev uuid-dev
    sudo apt-get install -y bison flex libcmocka-dev

    wget https://github.com/rurban/safeclib/releases/download/v08112019/libsafec-08112019.0-gad76c7.tar.gz
    tar -xzvf libsafec-08112019.0-gad76c7.tar.gz
    cd libsafec-08112019.0-gad76c7/
    ./configure
    make
    sudo make install

    cd ~/snort_src/
    wget https://ftp.pcre.org/pub/pcre/pcre-8.43.tar.gz
    tar -xzvf pcre-8.43.tar.gz
    cd pcre-8.43
    ./configure
    make
    sudo make install

    sudo apt-get install -y libunwind-dev
    cd ~/snort_src
    wget https://github.com/gperftools/gperftools/releases/download/gperftools-2.7.90/gperftools-2.7.90.tar.gz
    tar xzvf gperftools-2.7.90.tar.gz
    cd gperftools-2.7.90
    ./configure
    make
    sudo make install

    cd ~/snort_src
    wget http://www.colm.net/files/ragel/ragel-6.10.tar.gz
    tar -xzvf ragel-6.10.tar.gz
    cd ragel-6.10
    ./configure
    make
    sudo make install

    cd ~/snort_src
    wget https://dl.bintray.com/boostorg/release/1.72.0/source/boost_1_72_0.tar.gz
    tar -xvzf boost_1_72_0.tar.gz

    cd ~/snort_src
    wget https://github.com/intel/hyperscan/archive/v5.2.1.tar.gz
    tar -xvzf v5.2.1.tar.gz

    mkdir ~/snort_src/hyperscan-5.2.1-build
    cd hyperscan-5.2.1-build/

    cmake -DCMAKE_INSTALL_PREFIX=/usr/local -DBOOST_ROOT=~/snort_src/boost_1_72_0/ ../hyperscan-5.2.1
    make
    sudo make install

    cd ~/snort_src/hyperscan-5.2.1-build/
    ./bin/unit-hyperscan

    cd ~/snort_src
    wget https://github.com/google/flatbuffers/archive/v1.12.0.tar.gz \
    -O flatbuffers-v1.12.0.tar.gz
    tar -xzvf flatbuffers-v1.12.0.tar.gz
    mkdir flatbuffers-build
    cd flatbuffers-build
    cmake ../flatbuffers-1.12.0
    make
    sudo make install

# kali linux

## nmap

    nmap -h
        manual page
    nmap -v -sS -O 192.168.43.2
        -v  : untuk verbose supaya banyak keluar informasi
        -sS : scanning port dengan mengirim paket SYNC
        -O  : guess OS detection
    nmap -oN hasilNmap.txt 192.168.43.2
        create nmap file output
    nmap -sP 192.168.43.2/24
        discover host
    nmap -sA 192.168.43.2
        find out if host is protected by a firewall
    nmap -PN 192.168.43.2
        scan if firewall active
    nmap --iflist
        show ip/route
    sudo nmap -p21 -script ftp-brute.nse -script-args \ userdb=/usr/share/wordlists/nmap.lst,passdb=/usr/share/wordlists/nmap.lst 192.168.43.2
        ftp brute force
