# Maintainer: Aditya Shakya <adi1090x@gmail.com>

pkgname=archcraft-i3wm
pkgver=1.1
pkgrel=5
pkgdesc="i3wm Configurations for Archcraft"
url="https://github.com/angeloscosta/archcraft-i3wm"
arch=('any')
license=('GPL3')
makedepends=('git')
depends=('i3-gaps' 'nitrogen'
		'archcraft-skeleton'
		'alacritty' 'thunar' 'sublime-text-4'
		'rofi' 'polybar' 'dunst'
		'mpd' 'mpc'
		'maim' 'xclip' 'viewnior'
		'ksuperkey' 
		'betterlockscreen'
		'picom-ibhagwan-git' 
		'xfce-polkit' 
		'xfce4-power-manager' 
		'xorg-xsetroot'
)
conflicts=()
provides=("${pkgname}")
options=(!strip !emptydirs)
install="${pkgname}.install"

prepare() {
	cp -af ../files/. ${srcdir}
}

package() {
	local _config=${pkgdir}/etc/skel/.config/i3
	mkdir -p "$_config"

	# Copy i3wm config files
	cp -r ${srcdir}/alacritty 		"$_config"
	cp -r ${srcdir}/bin 			"$_config"
	cp -r ${srcdir}/polybar 		"$_config"
	cp -r ${srcdir}/rofi 			"$_config"
	cp -r ${srcdir}/wallpapers 		"$_config"

	chmod +x "$_config"/bin/*
	chmod +x "$_config"/rofi/bin/*

	install -Dm 644 config   		"$_config"/config
	install -Dm 644 dunstrc   		"$_config"/dunstrc
	install -Dm 644 picom.conf   	"$_config"/picom.conf
}
