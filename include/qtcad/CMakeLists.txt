set(qtcad_headers
  QAccordion.h
  QColorRGB.h
  QFlowLayout.h
  QKeyVal.h
  QToolPalette.h
  QViewCtrl.h
  QgDockWidget.h
  QgEdit.h
  QgModel.h
  QgTreeSelectionModel.h
  QgTreeView.h
  QgUtil.h
  QtAppExecDialog.h
  QtCADQuad.h
  QtCADView.h
  QtConsole.h
  QtConsoleListener.h
  QtGL.h
  QtSW.h
  SignalFlags.h
  defines.h
  gInstance.h
  )
BRLCAD_MANAGE_FILES(qtcad_headers ${INCLUDE_DIR}/brlcad/qtcad)

CMAKEFILES(CMakeLists.txt)

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
