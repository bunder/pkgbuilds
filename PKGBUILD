# CPAN Name  : Future
# Contributor: Anton Leontiev <scileont /at/ gmail.com>
# Generator  : CPANPLUS::Dist::Arch 1.32

pkgname=perl-future
pkgver=0.43
pkgrel=1
pkgdesc='Perl module to deal with operation awaiting completion'
arch=('any')
url='https://metacpan.org/release/Future'
license=('PerlArtistic' 'GPL')
makedepends=('perl-module-build>=0.4004')
checkdepends=('perl-test-fatal' 'perl-test-identity' 'perl-test-refcount')
depends=('perl>=5.15.8')
source=(http://search.cpan.org/CPAN/authors/id/P/PE/PEVANS/Future-0.43.tar.gz)
options=(!emptydirs)
md5sums=('3199b34cda8872086b614a36d8cdfbf7')

sanitize() {
	unset PERL5LIB PERL_MM_OPT PERL_MB_OPT PERL_LOCAL_LIB_ROOT
	export PERL_MM_USE_DEFAULT=1 MODULEBUILDRC=/dev/null
}

build() {
	cd Future-0.43
	sanitize
	perl Build.PL --installdirs vendor --destdir "$pkgdir"
	perl Build
}

check() {
	cd Future-0.43
	sanitize
	perl Build test
}

package() {
	cd Future-0.43
	sanitize
	perl Build install
	find "$pkgdir" \( -name .packlist -o -name perllocal.pod \) -delete
}
