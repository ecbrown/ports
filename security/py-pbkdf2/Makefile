COMMENT =	Python implementation of PBKDF2

MODPY_DISTV =	1.3
REVISION =		12
DISTNAME =		pbkdf2-${MODPY_DISTV}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		security devel

MAINTAINER =		Giannis Tsaraias <tsg@openbsd.org>

HOMEPAGE =		http://www.dlitz.net/software/python-pbkdf2/

# MIT
PERMIT_PACKAGE =	Yes

MODPY_PI = 		Yes
MODULES =		lang/python
MODPY_PYBUILD =	setuptools

TEST_ENV =		PYTHONPATH=${WRKBUILD}

do-test:
	cd ${WRKSRC}/test; ${SETENV} ${ALL_TEST_ENV} \
		${MODPY_BIN} ./test_pbkdf2.py

.include <bsd.port.mk>
