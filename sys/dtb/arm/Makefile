#	$NetBSD: Makefile,v 1.2 2020/05/23 13:24:08 skrll Exp $

DTSARCH=	arm
DTSGNUARCH=	arm

ARCHDTSDIR=	$S/external/gpl2/dts/dist/arch/arm/boot/dts

.if !empty(MACHINE_ARCH:Mearmv6*)
DTSMAKEVARS=	CONFIG_ARCH_BCM2835=y
.elif !empty(MACHINE_ARCH:Mearmv7*)
DTSMAKEVARS=	CONFIG_SOC_AM33XX=y		\
		CONFIG_ARCH_BCM2835=y		\
		CONFIG_ARCH_EXYNOS5=y		\
		CONFIG_SOC_IMX6Q=y		\
		CONFIG_MACH_MESON8=y		\
		CONFIG_ARCH_OMAP3=y		\
		CONFIG_ARCH_SOCFPGA=y		\
		CONFIG_MACH_SUN4I=y		\
		CONFIG_MACH_SUN5I=y		\
		CONFIG_MACH_SUN6I=y		\
		CONFIG_MACH_SUN7I=y		\
		CONFIG_MACH_SUN8I=y		\
		CONFIG_MACH_SUN9I=y		\
		CONFIG_ARCH_TEGRA_124_SOC=y	\
		CONFIG_ARCH_VEXPRESS=y		\
		CONFIG_ARCH_ZYNQ=y
.endif

DTSFILESCMD=	${MAKE} -C ${ARCHDTSDIR} ${DTSMAKEVARS} -v dtb-y
DTS=		${DTSFILESCMD:sh}


# Extra .dts files from arch/arm/dts
.if !empty(MACHINE_ARCH:Mearmv7*)
DTS+=		sun5i-r8-pocketchip.dts
DTS+=		sun7i-a20-olinuxino-lime2-emmc-spi.dts
DTS+=		sun8i-h2-plus-bananapi-p2-zero.dts
DTS+=		sun8i-h3-nanopi-r1.dts
.endif

.include <bsd.dtb.mk>
