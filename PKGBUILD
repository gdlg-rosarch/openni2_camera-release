# Script generated with Bloom
pkgdesc="ROS - Launch files to start the openni2_camera drivers using rgbd_launch."


pkgname='ros-lunar-openni2-launch'
pkgver='0.3.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('python2-catkin_pkg'
'ros-lunar-catkin'
)

depends=('ros-lunar-depth-image-proc'
'ros-lunar-image-proc'
'ros-lunar-nodelet'
'ros-lunar-openni2-camera'
'ros-lunar-rgbd-launch'
'ros-lunar-tf'
)

conflicts=()
replaces=()

_dir=openni2_launch
source=()
md5sums=()

prepare() {
    cp -R $startdir/openni2_launch $srcdir/openni2_launch
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

