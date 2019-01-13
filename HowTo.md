# CameraAravis Howto

## libaravisを0.6にアップ  
IPアドレスからカメラをサーチするには0.6にアップする必要あり。

1. PkgConfig  
インスト確認(多分入っている)。
~~~
pkg-config --version
~~~
Mint(Sonya)で0.29.1でした。

2. libaravis-0.6  
0.4と手順的には同じ。  
http://ftp.gnome.org/pub/GNOME/sources/aravis/0.6/  から  "aravis-0.6.0.tar.xz" をダウンロード。またはcurlコマンドで直接DLしてもいい
~~~
curl http://ftp.gnome.org/pub/GNOME/sources/aravis/0.6/aravis-0.6.0.tar.xz >aravis-0.6.0.tar.xz
~~~
展開してaravis...以下にcdし
~~~
./configure
make
sudo make install
~~~
カメラを接続し
~~~
arv-tool-0.6
~~~
カメラIDに加えてIPアドレスが表示される。

## ビルド  
普通に
~~~
catkin_make
~~~
このときどうしても0.4とリンクしてしまうことがある(0.4がアンインストされていればビルドエラーになる)。  
このときは~/cakin_ws/devel/下のキャッシュを消す。
~~~
rm -fR ~/catkin_ws/devel/lib/camera_aravis
~~~
