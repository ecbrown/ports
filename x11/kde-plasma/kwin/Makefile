COMMENT =	window manager for KDE Plasma Desktops
DISTNAME =	kwin-${VERSION}
REVISION =	0

SHARED_LIBS +=  kcmkwincommon             1.0 # 0.0
SHARED_LIBS +=  kwin                      1.0 # 0.0
SHARED_LIBS +=  kwineffects               1.0 # 0.0
SHARED_LIBS +=  kwinglutils               1.0 # 0.0
SHARED_LIBS +=  kwinxrenderutils          1.0 # 0.0

WANTLIB += ${COMPILER_LIBCXX} EGL GL ICE KF6Attica KF6AuthCore
WANTLIB += KF6ColorScheme KF6ConfigCore KF6ConfigGui KF6ConfigQml
WANTLIB += KF6ConfigWidgets KF6CoreAddons KF6Crash KF6DBusAddons
WANTLIB += KF6GlobalAccel KF6GuiAddons KF6I18n KF6IdleTime KF6KCMUtils
WANTLIB += KF6KCMUtilsCore KF6KCMUtilsQuick KF6NewStuffCore KF6NewStuffWidgets
WANTLIB += KF6Notifications KF6Package KF6Service KF6Svg KF6WidgetsAddons
WANTLIB += KF6WindowSystem KF6XmlGui KGlobalAccelD KWaylandClient
WANTLIB += PlasmaActivities Qt6Concurrent Qt6Core Qt6DBus Qt6Gui
WANTLIB += Qt6Network Qt6OpenGL Qt6OpenGLWidgets Qt6Qml Qt6QmlModels
WANTLIB += Qt6Quick Qt6Sensors Qt6Svg Qt6UiTools Qt6WaylandClient
WANTLIB += Qt6Widgets Qt6Xml SM X11 Xext Xi c canberra display-info
WANTLIB += drm eis epoll-shim epoxy fontconfig freetype gbm input
WANTLIB += kdecorations2 kdecorations2private lcms2 m pipewire-0.3
WANTLIB += qaccessibilityclient-qt6 udev wayland-client wayland-cursor
WANTLIB += wayland-server xcb xcb-composite xcb-cursor xcb-damage
WANTLIB += xcb-dri3 xcb-glx xcb-icccm xcb-keysyms xcb-present
WANTLIB += xcb-randr xcb-render xcb-shape xcb-shm xcb-sync xcb-xfixes
WANTLIB += xcb-xinerama xcb-xinput xcb-xkb xcvt xkbcommon xkbcommon-x11

MODKDE_TRANSLATIONS =	Yes
MODKDE_ICON_CACHE =	Yes
MODKDE_DOCS =		Yes

MODULES +=	lang/python

BUILD_DEPENDS =	devel/kf6/kdeclarative \
		misc/hwdata \
		wayland/xwayland \
		x11/kde-plasma/breeze>=${VERSION} \
		x11/kde-plasma/kscreenlocker>=${VERSION}

RUN_DEPENDS =	devel/desktop-file-utils \
		misc/hwdata \
		x11/kde-plasma/breeze>=${VERSION}

LIB_DEPENDS =	audio/libcanberra \
		devel/epoll-shim \
		devel/kf6/attica \
		devel/kf6/kauth \
		devel/kf6/kcmutils \
		devel/kf6/kcolorscheme \
		devel/kf6/kconfig \
		devel/kf6/kconfigwidgets \
		devel/kf6/kcoreaddons \
		devel/kf6/kcrash \
		devel/kf6/kdbusaddons \
		devel/kf6/kglobalaccel \
		devel/kf6/kguiaddons \
		devel/kf6/ki18n \
		devel/kf6/kidletime \
		devel/kf6/knewstuff \
		devel/kf6/knotifications \
		devel/kf6/kpackage \
		devel/kf6/kservice \
		devel/kf6/ksvg \
		devel/kf6/kwidgetsaddons \
		devel/kf6/kwindowsystem \
		devel/kf6/kxmlgui \
		graphics/lcms2 \
		multimedia/pipewire/pipewire,-libs \
		sysutils/libdisplay-info \
		sysutils/libudev-openbsd \
		wayland/libei \
		wayland/libinput-openbsd \
		wayland/wayland \
		x11/kde-plasma/kdecoration>=${VERSION} \
		x11/kde-plasma/kglobalacceld>=${VERSION} \
		x11/kde-plasma/kwayland>=${VERSION} \
		x11/kde-plasma/plasma-activities>=${VERSION} \
		x11/libqaccessibilityclient \
		x11/qt6/qtdeclarative \
		x11/qt6/qtsensors \
		x11/qt6/qtsvg \
		x11/qt6/qttools \
		x11/qt6/qtwayland \
		x11/xkbcommon

CXXFLAGS +=		-I${X11BASE}/include -I${LOCALBASE}/include/libepoll-shim/
MODCMAKE_LDFLAGS =	-L${X11BASE}/lib -L${LOCALBASE}/lib -lepoll-shim
CONFIGURE_ENV +=	KFWaylandServer_DIR=${MODQT6_LIBDIR}/cmake

DEBUG_PACKAGES =	${BUILD_PACKAGES}

# XXX Need more work
CONFIGURE_ARGS =	-DKWIN_BUILD_SCREENLOCKER=OFF

TEST_ENV +=		XDG_RUNTIME_DIR=${WRKBUILD}

TEST_IS_INTERACTIVE =	X11

PORTHOME =		${WRKDIR}

.include <bsd.port.mk>
