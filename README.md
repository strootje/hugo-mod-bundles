# Bundles

The bundles mod doesn't do anything of itself. It's a bundle loader.
Other modules can use this to easely load assets into certain hooks.

## Usage (website developer)

```bash
$ hugo mod get -u git.strooware.nl/hugo-mod-bundles
```

```html
<!DOCTYPE html>
<html lang="en">
	<head>
      <!-- ... -->
		{{- partial "bundle/head/end" . -}}
	</head>
	<body>
		{{- partial "bundle/body/start" . -}}

      <!-- ... -->

		{{- partial "bundle/body/end" . -}}
	</body>
</html>
```

## Usage (mod developer)

This module automaticaly pulls `scss` and `ts` files from the assets directory.
Use the following naming scheme's:
- assets/styles/bundle/\_*\_<head/body>_<start/end>.scss
- assets/scripts/bundle/\_*\_<head/body>_<start/end>.ts
- layouts/partials/bundle/\_\<key\>\_<head/body>_<start/end>.html

For partials you have to add a `key` in the list `[params.mod.bundles]`.
```toml
[params.mod.bundles]
testing = true

# Will check
# - partial "bundle/_testing_head_end" .
# - partial "bundle/_testing_body_start" .
# - partial "bundle/_testing_body_end" .
```

## Examples

The following hugo mods already use bundles:
- [hugo-mod-forkawesome](https://git.strooware.nl/hugo-mod-forkawesome)
- [hugo-mod-leaflet](https://git.strooware.nl/hugo-mod-leaflet)
- [hugo-mod-marquee](https://git.strooware.nl/hugo-mod-marquee)
- [hugo-mod-salonized](https://git.strooware.nl/hugo-mod-salonized)
- [hugo-mod-stackcss](https://git.strooware.nl/hugo-mod-stackcss)

And these site use the loading part:
- [jodiestains.com](https://jodiestains.com) ([source](https://git.strooware.nl/hugo-site-jodiestains))
- [strootje.com](https://strootje.com) ([source](https://git.strooware.nl/hugo-site-strootje))