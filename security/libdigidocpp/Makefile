PORTNAME=	libdigidocpp
DISTVERSION=	4.5.1
CATEGORIES=	security

DISTVERSIONPREFIX=	v
MAINTAINER=	andri.piik@gmail.com
COMMENT=	Library for creating and reading DigiDoc signature files
WWW=		https://github.com/breakingthings/libdigidocpp

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/LICENSE.LGPL

LIB_DEPENDS=	libxml2.so:textproc/libxml2

OPTIONS_DEFINE=	DOCS
DOCS_CMAKE_BOOL=	BUILD_DOCS
USES=		cmake gnome iconv ssl
USE_GNOME=	libxml2
CMAKE_ARGS+=	-DCMAKE_DEBUG_POSTFIX=""

USE_GITHUB=	yes
GH_ACCOUNT=	breakingthings
GH_PROJECT=	libdigidocpp
GH_TAGNAME=	6e64cec

.if !defined(WITH_DEBUG)
PLIST_SUB+=	DEBUG=""
.else
PLIST_SUB+=	DEBUG="@comment "
.endif

.include <bsd.port.mk>
