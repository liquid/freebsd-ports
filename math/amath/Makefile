# $FreeBSD$

PORTNAME=	amath
PORTVERSION=	1.6.2
CATEGORIES=	math
MASTER_SITES=	http://suyai.innolan.net/

MAINTAINER=	cs@innolan.dk
COMMENT=	Simple command line calculator

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

HAS_CONFIGURE=	yes
CONFIGURE_ARGS=	-Wno-inline-new-delete
MAKE_ARGS=	CC=${CC} CXX=${CXX}
PLIST_FILES=	bin/${PORTNAME}
ONLY_FOR_ARCHS=	aarch64 amd64 arm armv6 i386 powerpc

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/${PORTNAME}

do-test:
	${WRKSRC}/${PORTNAME} test

.include <bsd.port.mk>
