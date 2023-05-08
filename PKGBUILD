pkgbase=libdxvk-bin
pkgname=('libdxvk-bin' 'lib32-libdxvk-bin')
pkgver=2.1
pkgrel=1
pkgdesc="Native Linux port of DXVK to allow usage without WINE"
arch=('x86_64')
url="https://github.com/doitsujin/dxvk"
license=('ZLIB')
depends=(sdl2 vulkan-icd-loader lib32-sdl2 lib32-vulkan-icd-loader)
provides=(libdxvk_dxgi.so libdxvk_d3d9.so libdxvk_d3d11.so)
source=(
	"$url/releases/download/v$pkgver/dxvk-native-$pkgver-steamrt-sniper.tar.gz"
	"https://raw.githubusercontent.com/doitsujin/dxvk/v$pkgver/LICENSE"
)
sha256sums=(
	'8bc0880dfddb5768dcc0b8ebca0f1b2bba478681517247376fa2dbf87432740e'
	'03ca4af84f5cd28cef3ed3f1ef4d17996992d35ccdbe82b29cc020ca02c16f3d'
)

package_libdxvk-bin() {
	depends=(sdl2 vulkan-icd-loader)
	provides+=(libdxvk)
	conflicts=(libdxvk)

	find lib -name '*.so' \
		-exec install -Dm644 '{}' -t "$pkgdir/usr/lib/" \;
	install -Dm644 LICENSE -t "$pkgdir/usr/share/licenses/$pkgname"
}

package_lib32-libdxvk-bin() {
	pkgdesc+=" (32-bit)"
	depends=(lib32-sdl2 lib32-vulkan-icd-loader lib32-gcc-libs)
	provides+=(lib32-libdxvk)
	conflicts=(lib32-libdxvk)

	find lib32 -name '*.so' \
		-exec install -Dm644 '{}' -t "$pkgdir/usr/lib32/" \;
	install -Dm644 LICENSE -t "$pkgdir/usr/share/licenses/$pkgname"
}
