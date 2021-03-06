cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  libepos
  VERSION 0.1
  RELEASE alpha
  SUMMARY "Driver library for the maxon EPOS motor control."
  AUTHOR "Ralf Kaestner"
  CONTACT "ralf.kaestner@gmail.com"
  HOME "http://aslforge.ethz.ch/projects/libepos"
  LICENSE "BSD"
  PREFIX epos-
  INSTALL /usr
)

remake_doc(
  html
)

remake_pack_deb(
  tulibs libcan
)
remake_pack_deb(
  COMPONENT utils
  DESCRIPTION "utilities"
  libepos
)
remake_pack_deb(
  COMPONENT dev
  DESCRIPTION "development headers"
  tulibs-dev libcan-dev
)
remake_pack_deb(
  ARCH all
  COMPONENT doc
  DESCRIPTION "documentation"
)
