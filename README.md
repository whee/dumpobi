dumpobi
=======

`dumpobi` extracts some information from OBi100/OBi110 firmware
update files.

Usage
-----

    $ dumpobi ./OBi-1-3-0-2711.fw

      200 [favicon.ico] - 3468 bytes
      f9b [VS_1_VP_1_.xml] - 4618 bytes
     21b7 [listexpander.js] - 2978 bytes
     2d6c [green.png] - 5094 bytes
     415f [VS_1_CODEC_2_.xml] - 16882 bytes
     8366 [VS_1_X_STAR_2_.xml] - 6169 bytes
     9b95 [VS_1_VP_1_L_2_R_.xml] - 14497 bytes
     d44e [VS_1_.xml] - 576 bytes
    10100 [backup.xml] - 49258 bytes
    1c178 [index.htm] - 1107 bytes
    1c5d8 [HIDDEN.xml] - 5126 bytes
    20100 [VS_1_VP_1_L_1_.xml] - 14331 bytes
    23911 [VS_1_VP_1_SIP_.xml] - 16425 bytes
    27950 [left.htm] - 855 bytes
    27cb3 [obihai-logo.png] - 15554 bytes
    2b988 [DI_S_.xml] - 7814 bytes
    2d81b [expanded.gif] - 74 bytes
    30100 [DM_S_.xml] - 13919 bytes
    3376c [SPEEDDIAL_.xml] - 18865 bytes
    3812f [VS_1_VP_1_L_2_.xml] - 14328 bytes
    40100 [default.xsl] - 47202 bytes
    4b971 [VS_1_VP_2_.xml] - 4616 bytes
    50100 [VS_1_VP_2_T_.xml] - 13947 bytes
    5378f [header_bg.jpg] - 11172 bytes
    56344 [submit.htm] - 1555 bytes
    56965 [SetupWizard.xml] - 8252 bytes
    589b4 [VS_1_X_FXS_1_.xml] - 16552 bytes
    5ca71 [style.css] - 8996 bytes
    5eda2 [DM_MISC_.xml] - 3233 bytes
    60100 [VS_1_VP_1_T_.xml] - 13951 bytes
    63793 [VS_1_VP_2_RTP_.xml] - 1811 bytes
    63ebc [caution.png] - 5775 bytes
    6555a [VS_1_X_STAR_1_.xml] - 6169 bytes
    66d89 [VS_1_CODEC_1_.xml] - 16884 bytes
    6af92 [upload.jpg] - 743 bytes
    6b287 [listexpander.css] - 2078 bytes
    6bab9 [menu-obi100.htm] - 6534 bytes
    6d452 [menu.htm] - 6634 bytes
    6ee48 [VS_1_VP_1_RTP_.xml] - 1809 bytes
    70100 [VS_1_VP_1_L_1_R_.xml] - 14496 bytes
    739b8 [q.gif] - 2310 bytes
    742c7 [rowcolors.js] - 647 bytes
    7455e [VS_1_X_AA_1_.xml] - 12129 bytes
    774d3 [collapsed.gif] - 79 bytes
    77533 [VS_1_X_P2P_1_.xml] - 10760 bytes
    79f50 [DI_NS_.xml] - 13883 bytes
    7d599 [rebootconfig.htm] - 1288 bytes
    7dab5 [VS_1_VP_1_L_1_Stats.xml] - 4910 bytes
    80100 [VS_1_VP_2_SIP_.xml] - 16425 bytes
    8413f [VS_1_X_FXO_1_.xml] - 17861 bytes
    88719 [PI_FXS_1_Stats.xml] - 2892 bytes
    8927b [DIGITMAPS_.xml] - 5094 bytes
    8a673 [VS_1_X_GW_.xml] - 19362 bytes 

Output files are placed in a directory named
`<firmware file name>.extracted`.

Notes
-----

The files found account for ~30% of the data in the firmware image.
These entries have a simple structure:

    0xf3 | filename size (1 byte) | file size (1 short) | filename | data
    
The next file is either immediately following or after NULL padding.

The rest of the data in the image haven't been analyzed; these were
the most obvious.