# Maintainer: Ankit R Gadiya <arch@argp.in>
# Contributor: Joel Goguen <contact+aur@jgoguen.ca>

pkgname=ruby-jekyll-feed
pkgver=0.11.0
pkgrel=1
pkgdesc="A Jekyll plugin to generate an Atom (RSS-like) feed of your Jekyll posts"
arch=('any')
depends=('ruby' 'jekyll')
url="https://rubygems.org/gems/jekyll-feed"
noextract=("jekyll-feed-${pkgver}.gem")
license=('MIT')
source=("https://rubygems.org/downloads/jekyll-feed-${pkgver}.gem")
sha256sums=('97c52f737f6ff7c442277c1f2e525c6b1c76b699654bd711f4b6b53a17c6b486')

package() {
    local _gemdir="$(ruby -e'puts Gem.default_dir')"
    gem install --ignore-dependencies --no-user-install -i "${pkgdir}/${_gemdir}" -n "${pkgdir}/usr/bin" "jekyll-feed-${pkgver}.gem"
    rm "${pkgdir}/${_gemdir}/cache/jekyll-feed-${pkgver}.gem"

    install -Dm644 "${pkgdir}/${_gemdir}/gems/jekyll-feed-${pkgver}/LICENSE.txt" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
