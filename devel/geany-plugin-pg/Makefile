# $FreeBSD$

PORTNAME=	geany-plugin-pg
PORTVERSION=	${GEANY_VER}
PORTREVISION=	1
CATEGORIES=	devel

MAINTAINER=	madpilot@FreeBSD.org
COMMENT=	Geany plugin: ${${GEANY_PLUGIN}_DESC}

LIB_DEPENDS=	libgpgme.so:security/gpgme
RUN_DEPENDS=	gpg2:security/gnupg

.include "${.CURDIR}/../geany-plugins/files/Makefile.common"
.include <bsd.port.mk>
