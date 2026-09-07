PORTNAME=	libdigidocpp
DISTVERSION=	4.5.1
CATEGORIES=	security

DISTVERSIONPREFIX=	v
MAINTAINER=	andri.piik@gmail.com
COMMENT=	Library for creating and reading DigiDoc signature files
WWW=		https://github.com/breakingthings/libdigidocpp

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/LICENSE.LGPL

LIB_DEPENDS=	libxml2.so:textproc/libxml2 \
		libxmlsec1-openssl.so:security/xmlsec1

USES=		cmake gnome iconv ssl
USE_GNOME=	libxml2

OPTIONS_DEFINE= DOCS

DOCS_CMAKE_BOOL=        BUILD_DOCS
DOCS_BUILD_DEPENDS=     doxygen:devel/doxygen

DOCS_CMAKE_BOOL_OFF=	CMAKE_DISABLE_FIND_PACKAGE_Doxygen

CMAKE_ARGS+=	-DCMAKE_DISABLE_FIND_PACKAGE_SWIG:BOOL=TRUE

.include <bsd.port.options.mk>

.if defined(WITH_DEBUG)
PLIST_SUB+=		DEBUG_SUFFIX="d"
.else
PLIST_SUB+=		DEBUG_SUFFIX=""
.endif

USE_GITHUB=	yes
GH_ACCOUNT=	breakingthings
GH_PROJECT=	libdigidocpp
GH_TAGNAME=	104c77a

.if !defined(WITH_DEBUG)
PLIST_SUB+=	DEBUG=""
.else
PLIST_SUB+=	DEBUG="@comment "
.endif

.include <bsd.port.mk>
