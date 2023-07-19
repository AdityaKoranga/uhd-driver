# uhd-driver
```bash
sudo apt install -y libboost-all-dev libusb-1.0-0-dev doxygen python3-docutils python3-mako python3-numpy python3-requests python3-ruamel.yaml python3-setuptools cmake build-essential

git clone https://github.com/EttusResearch/uhd.git ~/uhd
cd ~/uhd
git checkout v4.4.0.0
cd host
mkdir build
cd build
cmake ../
make -j $(nproc)
make test # This step is optional
sudo make install
sudo ldconfig
sudo uhd_images_downloader
```
# NOTE
in the step `make -j $(nproc)` nproc will take all the cores, so instead, use few cores less than the total cores because it might also use the cores that are assigned to the other services/pods/containers.

for eg: if total cores are 40 then use 10 less, like the following
`make -j 30`
