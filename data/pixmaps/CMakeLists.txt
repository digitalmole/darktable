cmake_minimum_required(VERSION 2.6)

#
# Install fixed sized icons
#
set(FIXED_SIZES "16x16" "22x22" "24x24" "32x32" "48x48" "64x64" "256x256" "scalable")
foreach(pixmap_size ${FIXED_SIZES})
	# install apps icons
	FILE(GLOB PIXMAP_FILES ${CMAKE_CURRENT_SOURCE_DIR}/${pixmap_size}/*.png ${CMAKE_CURRENT_SOURCE_DIR}/${pixmap_size}/*.svg)
	install(FILES ${PIXMAP_FILES} DESTINATION ./share/icons/${THEME}/${pixmap_size}/apps)
endforeach(pixmap_size)

#
# Install plugin pixmaps
#
FILE(GLOB DARKROOM_PLUGIN_PIXMAPS "plugins/darkroom/*.png")
install(FILES ${DARKROOM_PLUGIN_PIXMAPS} DESTINATION ${SHARE_INSTALL}/darktable/pixmaps/plugins/darkroom )

FILE(GLOB OTHER_PIXMAPS "*.png")
install(FILES ${OTHER_PIXMAPS} DESTINATION ${SHARE_INSTALL}/darktable/pixmaps )
