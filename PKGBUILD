# Script generated with Bloom
pkgdesc="ROS - ROS device driver for Ifm O3M151 TOF camera."
url='http://www.ros.org/wiki/o3m151_driver'

pkgname='ros-kinetic-o3m151-driver'
pkgver='1.2.1_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('libpcap'
'ros-kinetic-catkin'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-nodelet'
'ros-kinetic-pcl-conversions'
'ros-kinetic-pcl-ros'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-roslaunch'
'ros-kinetic-roslib'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
)

depends=('libpcap'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-nodelet'
'ros-kinetic-pcl-conversions'
'ros-kinetic-pcl-ros'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-sensor-msgs'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=o3m151_driver
source=()
md5sums=()

prepare() {
    cp -R $startdir/o3m151_driver $srcdir/o3m151_driver
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

