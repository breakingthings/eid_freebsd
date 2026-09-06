PORTNAME=	digidoc4-client
DISTVERSION=	4.11.1
CATEGORIES=	security

DISTVERSIONPREFIX=	v
MAINTAINER=	andri.piik@gmail.com
COMMENT=	DigiDoc4 GUI client for signing and encrypting documents
WWW=		https://github.com/open-eid/DigiDoc4-Client

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/LICENSE.LGPL

LIB_DEPENDS=	libdigidocpp.so:security/libdigidocpp \
		libpcsclite.so:devel/pcsc-lite \
		libflatbuffers.so:devel/flatbuffers

USES=		cmake compiler:c++11-lang qt:5
USE_QT=		core gui widgets network svg

USE_GITHUB=	yes
GH_ACCOUNT=	open-eid
GH_PROJECT=	DigiDoc4-Client
GH_TUPLE=	open-eid:qt-common:f748156:qtcommon/qt-common \
		open-eid:libcdoc:83408f9:libcdoc/libcdoc

CMAKE_ARGS+=	-DCMAKE_DEBUG_POSTFIX=""


post-extract:
	@${RMDIR} ${WRKSRC}/common
	@${MV} ${WRKSRC}/qt-common ${WRKSRC}/common
	@${RMDIR} ${WRKSRC}/client/libcdoc
	@${MV} ${WRKSRC}/libcdoc ${WRKSRC}/client/libcdoc

.include <bsd.port.mk>
