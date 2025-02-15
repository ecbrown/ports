PORTROACH=	limit:^2\.28

COMMENT=	SSL library with an intuitive API and readable source code

GH_ACCOUNT=	ARMmbed
GH_PROJECT=	mbedtls
GH_TAGNAME=	mbedtls-2.28.0
DISTNAME=	${GH_TAGNAME}
REVISION=	1

# check SOVERSION
SHARED_LIBS +=  mbedtls		7.0
SHARED_LIBS +=  mbedcrypto	5.0
SHARED_LIBS +=  mbedx509	3.2

CATEGORIES=	security

HOMEPAGE=	https://tls.mbed.org/

# Apache v2 (or commercial license)
PERMIT_PACKAGE=	Yes

WANTLIB += c pthread

MODULES=	devel/cmake \
		lang/python

MODPY_RUNDEP=	No

CONFIGURE_ARGS=		-DUSE_SHARED_MBEDTLS_LIBRARY=ON \
			-DLINK_WITH_PTHREAD=ON

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/mbedtls
	cd ${WRKSRC}; ${INSTALL_DATA} README.md ChangeLog \
	    ${PREFIX}/share/doc/mbedtls
	mv ${PREFIX}/bin ${PREFIX}/share/examples/mbedtls
	(echo "These programs are useful code samples for a crypto expert, but";\
	echo "should not be relied upon by the normal end-user.") \
	> ${PREFIX}/share/examples/mbedtls/README

.include <bsd.port.mk>
