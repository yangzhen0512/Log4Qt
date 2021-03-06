# Change Log
All notable changes to this project will be documented in this file.
----

## [v1.4.0] - ??

### Added
- Environment variables starting with LOG4QT_ can now be used within a log4qt.properties file ${LOG4QT_...}

### Improvements
- Support static builds
- detect minimum required compiler version (log4qt depends on magic statics c++11)

## [v1.3.0] - 2016-09-13

### Added
- Changed directory layout
- Wrapper logger object for logging from Qml (QmlLogger)
- Appender for windows debug console (OutputDebugString)
- continuous integration windows - appveyor ci config files
- Changelog
- New global boolean property for *.properties files
    log4j.watchThisFile=[true]|[false]
    If set to true an file system watcher is installed for the *.properties file
    and the loggers are automatically reconfigured if this file changes.

### Improvements
- Replaced old-c-style casts
- Searching for *.properties files are extended:
  1. If <application binaryname.exe.log4qt.properties exists this file is used (Windows only)
  2. If <application binaryname>.log4qt.properties exists this file is used
  3. If "log4qt.properties" exists in the executables path this file is used
  4. If "log4qt.properties" exists in the current working directory this file is used (the default before)

### Fixed
- Minimum required Qt version is 5.3
- Reenabled an fixed unit test suite

## [v1.2.0] - 2016-05-03

### Added
- continuous integration linux - travis ci config files

### Improvment
- Replaced object ownership via LogObject and LogObjectPtr with QSharedPointer
- Removed pre Qt5 code
- Code improvements (use c++11 feature, e.g. nulptr, range base for loop, override, ...)
- Replaced msecSinceEpoch methods of DateTime with QDateTime methodes which exists since Qt4.7
- Replaced custom DataTime Formater with QDateTime::toString() - lost additional expression week

### Fixed
- converted inlcude file from utf-16 to ascii
- DatePatternConverter: fixed scope of toString() call

## [v1.1.0] - 2015-12-22

### Added
- Binary logger
- XMLLayout to support apache chainsaw
