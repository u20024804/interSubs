interSubs
=========

v. 2.1 - Changelog at the bottom.  
If Qt version doesn't work for you - use Tk https://github.com/oltodosel/interSubs/tree/master/Tk

-------

Interactive subtitles for `mpv`, that was made to help study languages.  
Easily tweaked and customizable.

- https://dict.cc/, https://pons.com/, http://reverso.net/, https://redensarten-index.de/ or Google for single words
- Offline \t separated dictionary. (https://github.com/ilius/pyglossary)
- https://www.deepl.com/translator for whole sentences.
- http://linguee.com/ redirecting to browser by click.
- https://forvo.com/, https://pons.com/ or Google for pronouncing single words.
- Can use multiple dictionaries simultaneously.
- Reassigning mouse buttons functions in config.
- Doesn't work with DVD (picture based) subtitles, only the text-based ones.
- To convert picture based subtitles into *.srt; also extracts them from *.mkv [extract_n_convert_dvd_bd_subtitles](https://github.com/oltodosel/extract_n_convert_dvd_bd_subtitles)
- Can extend time of subs showing; for slow readers
```
    00:02:23,046 --> 00:02:25,990
    bla bla
    00:02:28,020 --> 00:02:33,084
    waka waka
    
    00:02:23,046 --> 00:02:28,020
    bla bla
    00:02:28,020 --> 00:02:33,084
    waka waka
```

![z 00_00_5 75-00_00_19 96](https://user-images.githubusercontent.com/10230453/38359595-7f56acc0-38d1-11e8-9a65-257466a44e08.gif)

Requirements
------------
   - mpv 0.27 (I don't know if it will work with mpv front-ends.)
   - python 3
   - pyqt5 (pip/pacman/etc)
   - composite manager; xcompmgr or sth.
   - numpy (pip/pacman/etc)
   - beautifulsoup4 (pip/pacman/etc)
   - lua
   - socat
   - pkill
   - xdotool (for hiding subtitles when minimizing mpv or switching window) 
   - optional: chromium (for external translation, other browser can be specified)
   - optional: wget (for listening to pronunciation)

Installation
------------
```
mv interSubs.py interSubs.lua interSubs_config.py ~/.config/mpv/scripts/;
# Edit configuration file interSubs_config.py
# Edit interSubs.lua to add option where interSubs will start automatically. 
# For Mac also edit configuration at interSubs.lua
# For Windows - port it yourself.
```

Usage
-----
- Start video with mpv & select subtitles.
- Press F5 to start/stop interSubs.
- Point cursor over the word to get popup with translation.

Buttons bellow may be reassigned in config
-----
- Click on the word to look it up on another translator in the browser.
- Right-click on the word to hear its pronunciation.
- Wheel - scroll through transitions in popup.
- Wheel+Ctrl - resize subtitles.
- Wheel+Shift - change subtitles' vertical position.
- Wheel-click - cycle through auto_pause options.
- Wheel-click-left/right - +/- auto_pause_min_words. (fancy mouses)
- Back-click - translate whole sentence. (fancy mouses)

Important
-----
- May have issues working in a multi-monitor system.

Changelog
-----

* 2.0a
	* Configs are incompatible with previous version.
	* Tk is abandoned in favor of Qt.
		* Background can be fully transparent or semi/fully opaque.
		* Rendering is faster than with Tk.
		* requires pyqt5 for python 3
			* `pip install pyqt5` / `pacman -S python-pyqt5`
		* requires composite manager for not solid bg; `xcompmgr` or sth.
		* tested on Openbox, i3, KDE(kwin).
		* On KDE(kwin) go to composite and uncheck "Allow applications to block compositing". https://iwf1.com/wordpress/wp-content/uploads/2017/09/Disable-applications-override-compositor-KDE.jpg
	* No more stalling when pointing on a wrong word; those words will be translated and saved in background.
	* R2L isn't ready yet.
	* Option to not save translations on the disk was removed.
	* Noun colorization was removed.
	* Randomization of translations was removed.
	* Option to show N of previous subtitles is suspended for now, I might add it in the future.
	* Tk version won't be updated unless something critical happens.
* 2.1
	* R2L support (checked on Hebrew; works more or less).
	* Minor corrections.
