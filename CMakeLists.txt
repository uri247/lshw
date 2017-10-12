cmake_minimum_required(VERSION 3.8)
project(lshw)

set(CMAKE_CXX_STANDARD 11)

set(SOURCE_FILES
        src/core/abi.cc
        src/core/abi.h
        src/core/blockio.cc
        src/core/blockio.h
        src/core/burner.cc
        src/core/burner.h
        src/core/cdrom.cc
        src/core/cdrom.h
        src/core/config.h
        src/core/cpufreq.cc
        src/core/cpufreq.h
        src/core/cpuid.cc
        src/core/cpuid.h
        src/core/cpuinfo.cc
        src/core/cpuinfo.h
        src/core/db.cc
        src/core/db.h
        src/core/device-tree.cc
        src/core/device-tree.h
        src/core/disk.cc
        src/core/disk.h
        src/core/display.cc
        src/core/display.h
        src/core/dmi.cc
        src/core/dmi.h
        src/core/dump.cc
        src/core/dump.h
        src/core/fat.cc
        src/core/fat.h
        src/core/fb.cc
        src/core/fb.h
        src/core/heuristics.cc
        src/core/heuristics.h
        src/core/hw.cc
        src/core/hw.h
        src/core/ide.cc
        src/core/ide.h
        src/core/ideraid.cc
        src/core/ideraid.h
        src/core/isapnp.cc
        src/core/isapnp.h
        src/core/jedec.cc
        src/core/jedec.h
        src/core/lvm.cc
        src/core/lvm.h
        src/core/main.cc
        src/core/main.h
        src/core/mem.cc
        src/core/mem.h
        src/core/mounts.cc
        src/core/mounts.h
        src/core/network.cc
        src/core/network.h
        src/core/options.cc
        src/core/options.h
        src/core/osutils.cc
        src/core/osutils.h
        src/core/parisc.cc
        src/core/parisc.h
        src/core/partitions.cc
        src/core/partitions.h
        src/core/pci.cc
        src/core/pci.h
        src/core/pcmcia-legacy.cc
        src/core/pcmcia-legacy.h
        src/core/pcmcia.cc
        src/core/pcmcia.h
        src/core/pnp.cc
        src/core/pnp.h
        src/core/print.cc
        src/core/print.h
        src/core/s390.cc
        src/core/s390.h
        src/core/scsi.cc
        src/core/scsi.h
        src/core/smp.cc
        src/core/smp.h
        src/core/spd.cc
        src/core/spd.h
        src/core/sysfs.cc
        src/core/sysfs.h
        src/core/usb.cc
        src/core/usb.h
        src/core/version.cc
        src/core/version.h
        src/core/vio.cc
        src/core/vio.h
        src/core/virtio.cc
        src/core/virtio.h
        src/core/volumes.cc
        src/core/volumes.h
        src/lshw.cc)

include_directories(.)
include_directories(src)
include_directories(src/core)
include_directories(src/gui)

add_executable(lshw ${SOURCE_FILES})

set(CMAKE_EXE_LINKER_FLAGS "-static")

add_definitions(-DDATADIR="")
add_definitions(-DPNPVENDORS_PATH="")
add_definitions(-DSQLITE)

target_link_libraries(lshw sqlite3 pthread dl resolv)