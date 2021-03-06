# $FreeBSD$

PORTNAME=	seafile-client
PORTVERSION=	6.0.2
DISTVERSIONPREFIX=	v
CATEGORIES=	net-mgmt

MAINTAINER=	ultima1252@gmail.com
COMMENT=	Open Source Cloud Storage (Client)

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

BUILD_DEPENDS=	valac:lang/vala
LIB_DEPENDS=	libsearpc.so:devel/libsearpc \
		libevhtp.so:www/libevhtp \
		libzdb.so:databases/libzdb \
		libcurl.so:ftp/curl \
		libinotify.so:devel/libinotify \
		libccnet.so:net-mgmt/ccnet-client \
		libevent.so:devel/libevent2 \
		libuuid.so:misc/e2fsprogs-libuuid \
		libjansson.so:devel/jansson
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}sqlite3>0:databases/py-sqlite3 \
		${PYTHON_PKGNAMEPREFIX}urllib3>0:net/py-urllib3 \
		bash:shells/bash

CONFLICTS=	seafile-server-[0-9]*

USE_GITHUB=	yes
GH_ACCOUNT=	haiwen
GH_PROJECT=	seafile

USES=		autoreconf gettext iconv libarchive libtool mysql pathfix \
		pkgconfig python:-2.7 shebangfix sqlite ssl
USE_GNOME=	glib20
SHEBANG_FILES=	*.sh scripts/*.sh integration-tests/*.sh
GNU_CONFIGURE=	yes
USE_LDCONFIG=	yes
CONFIGURE_ENV=	SSL_CFLAGS="${OPENSSLINC}" SSL_LIBS="-L${OPENSSLLIB} -lssl -lcrypto"

INSTALL_TARGET=	install-strip
CPPFLAGS+=	-I${LOCALBASE}/include -I${LOCALBASE}/include/evhtp
LDFLAGS+=	-L${LOCALBASE}/lib

.include <bsd.port.options.mk>

post-patch:
# Fix P_KTHREAD r295435
.if ${OSVERSION} >= 1100097
	${REINPLACE_CMD} 's/P_KTHREAD/P_KPROC/' ${WRKSRC}/lib/utils.c
.endif

.include <bsd.port.mk>
