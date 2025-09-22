# ODR-AudioEnc-NonStandard
This is a fork of [ODR-AudioEnc](https://github.com/Opendigitalradio/ODR-AudioEnc) with added changes to provide compatibility with third-party, non-standard muxes. Those changes won't find place in ODR-AudioEnc itself, that aims to be fully standard-compliant.

Those muxes are currently supported:
- Itel ID MUX (both v5 and v6)

This fork will be updated from the upstream master branch, so each time there is a new upstream release.

## Documentation
You can refer to [the upstream README](https://github.com/Opendigitalradio/ODR-AudioEnc/blob/master/README.md) for any instruction about compiling and using the software.

Those additional command-line parameters are available:
 - `--itel-v5`: Apply the byte mapping and tag names to be compatible with an Itel ID ENC v5.
 - `--itel-v6`: Apply the byte mapping and tag names to be compatible with an Itel ID ENC v6.

Choosing which one to use depends on the mux you're streaming to. As of today, it seems that the vast majority of Itel muxes will only accept v6, but there are some of them still accepting both. You should probably start by trying `--itel-v6`, and fallback on `--itel-v5` if it doesn't work.

Those settings are currently global and will apply to all of the destinations. It's in my plans to turn it into a per-destination setting someday, so that you can have a single ODR-AudioEnc instance stream to both standard and non-standard encoders at the same time.

## Legal notice
This project is, and will always stay, on the legal side. All the changes are and will be made through reverse engineering, stream analysis and any technique that is legal in the Netherlands, where I live. I will refuse, under any circumstance, to use any information that comes from stolen code or specifications, or from manifacturers insiders. PRs are very welcome, but you must be able to prove you respected those conditions, and take your responsibility on it.
