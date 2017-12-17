# CPAN Name  : XML::Compile::SOAP
# Contributor: Anton Leontiev <scileont /at/ gmail.com>
# Generator  : CPANPLUS::Dist::Arch 1.32

pkgname=perl-xml-compile-soap
pkgver=3.22
pkgrel=1
pkgdesc='Perl package for SOAP implementations'
arch=('any')
url='https://metacpan.org/release/XML-Compile-SOAP'
license=('PerlArtistic' 'GPL')
depends=(
	'perl-xml-compile>=1.58'
	'perl-xml-compile-tester>=0.90'
	'perl-xml-compile-cache>=1.03'
	'perl-log-report>=1.05'
	'perl-libwww>=6.08'
	'perl-net-http>=6.16'
	'perl-file-slurp-tiny')
source=(http://search.cpan.org/CPAN/authors/id/M/MA/MARKOV/XML-Compile-SOAP-3.22.tar.gz)
options=(!emptydirs)
md5sums=('d6ead08c6574c62a38bd969ea2475a74')

sanitize() {
	unset PERL5LIB PERL_MM_OPT PERL_MB_OPT PERL_LOCAL_LIB_ROOT
	export PERL_MM_USE_DEFAULT=1
}

build() {
	cd XML-Compile-SOAP-3.22
	sanitize
	/usr/bin/perl Makefile.PL INSTALLDIRS=vendor
	make
}

check() {
	cd XML-Compile-SOAP-3.22
	sanitize
	make test
}

package() {
	cd XML-Compile-SOAP-3.22
	sanitize
	make install DESTDIR="$pkgdir"
	find "$pkgdir" -name .packlist -o -name perllocal.pod -delete
}
