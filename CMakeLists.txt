cmake_minimum_required(VERSION 3.8 FATAL_ERROR)

if(APPLE AND NOT CMAKE_OSX_DEPLOYMENT_TARGET)
    set(CMAKE_OSX_DEPLOYMENT_TARGET "10.13" CACHE STRING "" FORCE)
endif()

project(testdisk LANGUAGES C CXX)

file(GLOB SRC_FILES ${PROJECT_SOURCE_DIR}/src/file_scanner/*.c)

add_library(file_scanner ${SRC_FILES} )

target_include_directories(file_scanner
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
    PUBLIC ${CMAKE_SOURCE_DIR}/src
)

set(HEADERS
    src/addpart.h
    src/addpartn.h
    src/adv.h
    src/alignio.h
    src/analyse.h
    askloc.h
    autoset.h
    bfs.h
    bsd.h
    btrfs.h
    chgarch.h
    chgarchn.h
    chgtype.h
    chgtypen.h
    common.h
    cramfs.h
    crc.h
    dfxml.h
    dimage.h
    dir.h
    dirn.h
    dirpart.h
    diskacc.h
    diskcapa.h
    edit.h
)

add_definitions("-DHAVE_CONFIG_H -DHAVE_STRING_H -DHAVE_STDLIB_H")

add_executable(${PROJECT_NAME}
    src/addpart.c
    src/addpartn.c
    src/adv.c
    src/analyse.c
    src/askloc.c
    src/autoset.c
    src/bfs.c
    src/bsd.c
    src/btrfs.c
    src/chgarch.c
    src/chgarchn.c
    src/chgtype.c
    src/chgtypen.c
    src/common.c
    src/cramfs.c
    src/crc.c
    src/dfxml.c
    src/dimage.c
    src/dir.c
    src/dirn.c
    src/dirpart.c
    src/diskacc.c
    src/diskcapa.c
    src/edit.c
    src/ewf.c
    src/exfat.c
    src/exfat_dir.c
    src/exfatp.c
    src/ext2.c
    src/ext2_common.c
    src/ext2_dir.c
    src/ext2_sb.c
    src/ext2_sbn.c
    src/ext2grp.c
    src/ext2p.c
    src/f2fs.c
    src/fat.c
    src/fat1x.c
    src/fat32.c
    src/fat_adv.c
    src/fat_cluster.c
    src/fat_common.c
    src/fat_dir.c
    src/fat_unformat.c
    src/fatn.c
    src/fatp.c
    src/fatx.c
    src/fnctdsk.c
    src/fuzzerfidentify.cpp
    src/geometry.c
    src/geometryn.c
    src/gfs2.c
    src/godmode.c
    src/hdaccess.c
    src/hdcache.c
    src/hdwin32.c
    src/hfs.c
    src/hfsp.c
    src/hidden.c
    src/hiddenn.c
    src/hpa_dco.c
    src/hpfs.c
#    src/icon_ph.rc
#    src/icon_qph.rc
#    src/icon_tst.rc
    src/intrf.c
    src/intrface.c
    src/intrfn.c
    src/io_redir.c
    src/iso.c
    src/jfs.c
    src/list_sort.c
    src/log.c
    src/log_part.c
    src/luks.c
    src/lvm.c
    src/md.c
    src/memmem.h
    src/misc.c
    src/msdos.c
    src/netware.c
    src/next.c
    src/nodisk.c
    src/ntfs.c
    src/ntfs_adv.c
    src/ntfs_dir.c
    src/ntfs_fix.c
    src/ntfs_io.c
    src/ntfs_udl.c

    src/ntfs_utl.c
    src/ntfsp.c
    src/partauto.c
    src/partgpt.c
    src/partgptn.c
#TODO:    src/partgptro.c
    src/partgptw.c
    src/parthumax.c
    src/parti386.c
    src/parti386n.c
    src/partmac.c
    src/partmacn.c
    src/partnone.c
    src/partsun.c
    src/partsunn.c
    src/partxbox.c
    src/partxboxn.c
    src/pbanner.c
    src/pblocksize.c
    src/pdisksel.c
    src/pdiskseln.c
    src/pfree_whole.c
    src/phbf.c
    src/phbs.c
    src/phcfg.c
    src/phcli.c
#    src/phmain.c
    src/phnc.c
    src/photorec.c
    src/phrecn.c
    src/poptions.c
    src/ppartseln.c
    src/psearchn.c

#    src/qmainrec.cpp
#    src/qphbs.cpp
#    src/qphotorec.cpp
#    src/qphotorec.h
#    qphotorec.qrc
#    qphotorec_locale.qrc
#    src/qpsearch.cpp

    src/filegen.c
    src/refs.c
    src/rfs.c
    src/rfs_dir.c
    src/savehdr.c
    src/sessionp.c
    src/setdate.c
    src/sudo.c
    src/sun.c
    src/suspend.c
    src/suspend_no.c
    src/swap.c
    src/sysv.c
    src/tanalyse.c
    src/tbanner.c
    src/tdelete.c
    src/tdiskop.c
    src/tdisksel.c
    src/testdisk.c
    src/texfat.c
    src/thfs.c
    src/tload.c
    src/tlog.c
    src/tmbrcode.c
    src/tntfs.c
    src/toptions.c
    src/tpartwr.c
    src/ufs.c
    src/unicode.c
    src/vmfs.c
    src/wbfs.c

#    win32.c
#    win32.h
    src/xfs.c
    src/zfs.c

)

target_link_libraries(${PROJECT_NAME} file_scanner)

target_include_directories(${PROJECT_NAME}
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/file_scanner
)
