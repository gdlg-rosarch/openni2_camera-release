# Script generated with Bloom
pkgdesc="ROS - Drivers for the Asus Xtion and Primesense Devices. For using a kinect with ROS, try the <a href="http://wiki.ros.org/freenect_stack">freenect stack</a>"


pkgname='ros-lunar-openni2-camera'
pkgver='0.3.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('openni2'
'ros-lunar-camera-info-manager'
'ros-lunar-catkin'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-image-transport'
'ros-lunar-message-generation'
'ros-lunar-nodelet'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
)

depends=('openni2'
'ros-lunar-camera-info-manager'
'ros-lunar-dynamic-reconfigure'
'ros-lunar-image-transport'
'ros-lunar-message-runtime'
'ros-lunar-nodelet'
'ros-lunar-roscpp'
'ros-lunar-sensor-msgs'
)

conflicts=()
replaces=()

_dir=openni2_camera
source=()
md5sums=()

prepare() {
    cp -R $startdir/openni2_camera $srcdir/openni2_camera
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

