# 在ubuntu快速构建

```bash
# 工具
sudo apt install build-essential cmake pkg-config libevdev-dev libudev-dev libconfig++-dev libglib2.0-dev

git clone https://github.com/Code-Dramatist/logiops.git && cd logiops

mkdir build && cd build

cmake -DCMAKE_BUILD_TYPE=Release ..

make

sudo make install

# 添加 M720 配置 # 用的默认配置位置，也可以‵-c‵指定配置文件
cp ../../self-flow/logid.cfg /etc/logid.cfg

# 加入开机自启动
sudo cp logid.service /etc/systemd/system/
sudo systemctl daemon-reload
sudo systemctl enable logid
sudo systemctl enable --now logid

```