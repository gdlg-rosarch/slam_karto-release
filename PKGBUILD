# Script generated with Bloom
pkgdesc="ROS - This package pulls in the Karto mapping library, and provides a ROS wrapper for using it."


pkgname='ros-kinetic-slam-karto'
pkgver='0.7.3_1'
pkgrel=1
arch=('any')
license=('LGPL'
)

makedepends=('eigen3'
'ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-message-filters'
'ros-kinetic-nav-msgs'
'ros-kinetic-open-karto'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-sparse-bundle-adjustment'
'ros-kinetic-tf'
'ros-kinetic-visualization-msgs'
)

depends=('eigen3'
'ros-kinetic-message-filters'
'ros-kinetic-nav-msgs'
'ros-kinetic-open-karto'
'ros-kinetic-rosconsole'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-sparse-bundle-adjustment'
'ros-kinetic-tf'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=slam_karto
source=()
md5sums=()

prepare() {
    cp -R $startdir/slam_karto $srcdir/slam_karto
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

