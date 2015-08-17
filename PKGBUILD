# Maintainer: Jason St. John <jstjohn .. purdue . edu>
# Contributor: François Charette <firmicus ατ gmx δοτ net>

_perlmod=CGI-FormBuilder
_modnamespace=CGI
pkgname=perl-cgi-formbuilder
pkgver=3.09
pkgrel=3
pkgdesc="CGI::FormBuilder - Easily generate and process stateful forms"
arch=('any')
url="http://search.cpan.org/dist/${_perlmod}"
license=('GPL' 'PerlArtistic')
optdepends=('perl-cgi-session>=3.95: for CGI::FormBuilder::Multi'
            'perl-cgi-ssi>=0.92: for CGI::FormBuilder::Template::CGI_SSI'
            'perl-html-template>=2.06: for CGI::FormBuilder::Template::HTML'
            'perl-template-toolkit>=2.08: for CGI::FormBuilder::Template::TT2'
            'perl-text-template>=1.43: for CGI::FormBuilder::Template::Text')
options=('!emptydirs')
source=("http://cpan.org/modules/by-module/${_modnamespace}/${_perlmod}-${pkgver}.tgz")
sha512sums=('6907131de95ac0188a4a80e380fd81554bd9fb8d2566e961e5ff05a30e4498bccb157ecfdc77bdcd05427ebc5882caaea47b044aaaddae85f48231c0b7eef240')

build() {
	cd "${_perlmod}-${pkgver}"

	# Install module in vendor directories.
	PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor
	make
}

check() {
	cd "${_perlmod}-${pkgver}"
	make test
}

package() {
	cd "${_perlmod}-${pkgver}"
	make install DESTDIR="${pkgdir}"
}
