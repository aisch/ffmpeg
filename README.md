FFMPEG
========

Installs FFMPEG from source code with the following libs:
- libfdk-aac
- libspeex
- libopus
- libvpx
- libtheora
- libvorbis
- libmp3lame
- x264
- yasm

Installation
--------------

`ansible-galaxy install palkan.ffmpeg`

Role Variables
--------------

`defaults/main.yml`

| Name                        | Default Value | Description                                                      |
|-----------------------------|---------------|------------------------------------------------------------------|
| ffmpeg_source_dir           | /usr/local/src | Sources path                                                    |
| ffmpeg_build                | /usr/local/ffmpeg_build | Build path                                             |
| ffmpeg_bin_dir              | /usr/local/bin | Binaries path                                                   |
| ffmpeg_install_dir          | n/a | Make install DESTDIR                                                       |
| ffmpeg_env                  | PKG_CONFIG_PATH: "{{ ffmpeg_build }}/lib/pkgconfig" | Environment vars           |
| ffmpeg_flags                | ... (see source) | FFMPEG compilation flags                                      |
| ffmpeg_version              | HEAD | FFMPEG source version                                                     |
| ffmpeg_fdk_aac_version      | HEAD | FDKAAC source version                                                     |
| ffmpeg_opus_version         | HEAD | Opus source version                                                       |
| ffmpeg_speex_version        | HEAD | Speex source version                                                      |
| ffmpeg_x264_version         | HEAD | x264 source version                                                       |
| ffmpeg_vpx_version          | HEAD | VPX source version                                                        |
| ffmpeg_yasm_version         | HEAD | YASM source version                                                       |
| ffmpeg_x264_bin             | yes | Whether to install x264 binaries                                           |
| ffmpeg_yasm_bin             | yes | Whether to install yasm binaries                                           |
| ffmpeg_make_jobs            | 1 | Number of make jobs (-j)                                                     |
| ffmpeg_clean                | yes | Whether to delete all intermediate files (make disclean)                   |

Example Playbook
-------------------------

    - hosts: servers
      roles:
         - palkan.ffmpeg