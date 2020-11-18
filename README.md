# MakeLinuxLessShitty
What i did to make linux less shitty



# Fonts


- Install Ubuntu fonts, use Ubuntu Regular for UI
- For monospaces fonts, use the one you like (I choose Meslo LG M https://github.com/andreberg/Meslo-Font)
- For emojis, install Noto Color Emoji

Some websites expect Apple or Windows fonts, and fallback to shitty fonts (just like GitHub and Twitter for example), how to fix that?

Easy

- ``sudo gedit /etc/fonts/conf.d/99-fix-stupid-fonts.conf``
- Put this content: (Replace Ubuntu with what ever regular font you want, and replace Meslo LG M with whatever monospaced font you like)

``` xml
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>

  <match target="pattern">
    <test qual="any" name="family"><string>Segoe UI Emoji</string></test>
    <edit name="family" mode="assign" binding="same"><string>Noto Color Emoji</string></edit>
  </match>
  
  <!-- Aliasses -->
   <alias>
    <family>serif</family>
    <prefer>
      <family>Ubuntu</family>
    </prefer>
  </alias>
  <alias>
    <family>sans-serif</family>
    <prefer>
      <family>Ubuntu</family>
    </prefer>
  </alias>
  <alias>
    <family>sans</family>
    <prefer>
      <family>Ubuntu</family>
    </prefer>
  </alias>
  <alias>
    <family>monospace</family>
    <prefer>
      <family>Meslo LG M</family>
    </prefer>
  </alias>
  
  
  <!-- Replace -->
  <alias>
    <family>Segoe UI Emoji</family>
    <prefer><family>Noto Color Emoji</family></prefer>
  </alias>
  
  <alias>
    <family>Arial</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  
  <alias>
    <family>Consolas</family>
    <prefer><family>Meslo LG M</family></prefer>
  </alias>
  <alias>
    <family>Lucida Console</family>
    <prefer><family>Meslo LG M</family></prefer>
  </alias>
  <alias>
    <family>Menlo</family>
    <prefer><family>Meslo LG M</family></prefer>
  </alias>
  <alias>
    <family>monospace</family>
    <prefer><family>Meslo LG M</family></prefer>
  </alias>
  <alias>
    <family>Courier New</family>
    <prefer><family>Meslo LG M</family></prefer>
  </alias>
  <alias>
    <family>Lucida Sans</family>
    <prefer><family>Meslo LG M</family></prefer>
  </alias>
  <alias>
    <family>Lucida Sans Typewriter</family>
    <prefer><family>Meslo LG M</family></prefer>
  </alias>
  <alias>
    <family>monospace</family>
    <prefer><family>Meslo LG M</family></prefer>
  </alias>
  <alias>
    <family>Liberation Mono</family>
    <prefer><family>Meslo LG M</family></prefer>
  </alias>
  
  <alias>
    <family>Georgia</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Tahoma</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Trebuchet MS</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Comic Sans MS</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Times New Roman</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Verdana</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Lucida Grande</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Impact</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Helvetica</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Courier</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  <alias>
    <family>Segoe UI</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  
  <alias>
    <family>Verdana</family>
    <prefer><family>Ubuntu</family></prefer>
  </alias>
  
</fontconfig>
``` 

- Press Save and close gedit
- ``fc-cache -rfv``
- ``sudo dpkg-reconfigure fontconfig``
- Reboot your computer



# Audio

Audio on linux SUCKS, here is how to fix it, it's easy

- Install pulseeffects https://github.com/wwmm/pulseeffects
- Run pulseeffects
- Select: Limiter, Compressor, Loudness Compensator
- Reboot your computer


That's it, enjoy your less shitty Linux experience
