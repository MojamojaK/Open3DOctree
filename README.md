# Open3DPointCloudNormalEstimation

## 環境設定

### MacOS

#### サブモジュールの更新
```
git submodule update --init --recursive
```

#### Open3Dのインストール
```
cd third-party/Open3D
util/scripts/install-deps-osx.sh

mkdir build
cd build

cmake ../ -DCMAKE_BUILD_TYPE=Debug -DCMAKE_INSTALL_PREFIX=$(pwd)/../ -DBUILD_PYBIND11=OFF -DBUILD_PYTHON_MODULE=OFF -DBUILD_SHARED_LIBS=ON

make -j$(sysctl -n hw.physicalcpu)

make install

cd ../../../
```

#### プロジェクトビルド
```
mkdir build
cd build
cmake ../ -DCMAKE_BUILD_TYPE=Debug -DCMAKE_PREFIX_PATH=$(pwd)/../third-party/Open3D/lib/cmake/
make -j$(sysctl -n hw.physicalcpu)
cd ../
```