COMMENT =		Python last.fm library

MODPY_DISTV =	5.3.0
DISTNAME =		pylast-${MODPY_DISTV}
PKGNAME =		py-last-${MODPY_DISTV}
CATEGORIES =		audio net
REVISION =		0

HOMEPAGE =		https://github.com/pylast/pylast

# Apache 2.0
PERMIT_PACKAGE =	Yes

MODPY_PI =		Yes
MODPY_PYBUILD =		hatch-vcs

MODULES =		lang/python

RUN_DEPENDS =		www/py-httpx

TEST_DEPENDS =		${FULLPKGNAME}:${BUILD_PKGPATH} \
			devel/py-flaky \
			devel/py-test-cov \
			textproc/py-yaml

pre-test:
	@if ! [ -r ${WRKSRC}/test_pylast.yaml ]; then echo; \
		echo "Most tests will be skipped unless you provide a last.fm account"; \
		echo "to write test data to. Copy example_test_pylast.yaml to test_pylast.yaml"; \
		echo "and edit. See https://github.com/pylast/pylast?tab=readme-ov-file#testing"; \
	echo; fi

.include <bsd.port.mk>
