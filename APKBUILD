# Maintainer: Saikat Saha <ssaikatsaha1996@gmail.com>

pkgname=soc-qcom-sm8350
pkgver=1.0
pkgrel=1
pkgdesc="Common package for Qualcomm SM8350 devices"
url="https://postmarketos.org"
license="BSD-3-Clause"
arch="aarch64"
options="!check !archcheck !tracedeps"
depends="
	msm-modem-uim-selection
	bootmac
        swclock-offset
"
replaces="upower"
subpackages="$pkgname-nonfree-firmware:nonfree_firmware"
source="
	60-gpu-firmware.files
	UPower.conf
"

package() {
	# Shutdown when battery is critical instead of sleep
	install -Dm644 "$srcdir"/UPower.conf \
		"$pkgdir"/etc/UPower/UPower.conf
}

nonfree_firmware() {
	pkgdesc="Modem, WiFi and GPU Firmware"
	depends="msm-modem pd-mapper pd-mapper-openrc tqftpserv tqftpserv-openrc"
	install -Dm644 "$srcdir/60-gpu-firmware.files" \
		"$subpkgdir/usr/share/mkinitfs/files/60-gpu-firmware.files"
	install="$subpkgname.post-install"
}

sha512sums=""
