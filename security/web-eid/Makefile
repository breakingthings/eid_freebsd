PORTNAME=	web-eid
DISTVERSION=	2.10.0
CATEGORIES=	security www

DISTVERSIONPREFIX=	v
MAINTAINER=	andri.piik@gmail.com
COMMENT=	Web eID native messaging host for browser integration
WWW=		https://github.com/open-eid/web-eid-app

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libpcsclite.so:devel/pcsc-lite \
		libgtest.so:devel/googletest

USES=		cmake compiler:c++17-lang pkgconfig qt:6 ssl
USE_QT=		base svg tools:build

USE_GITHUB=	yes
GH_ACCOUNT=	web-eid
GH_PROJECT=	web-eid-app
GH_TUPLE=	web-eid:libelectronic-id:cea14db:lib/libelectronic-id

post-extract:
	@${RMDIR} ${WRKSRC}/lib/libelectronic-id
	@${MV} ${WRKSRC}/libelectronic-id ${WRKSRC}/lib/libelectronic-id

CMAKE_ARGS=	-D BUILD_TESTS=OFF \
		-D CMAKE_INSTALL_PREFIX=${PREFIX}
.include <bsd.port.mk>
