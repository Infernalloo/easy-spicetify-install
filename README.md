# Easy guide to install spicetify on Linux

## Step 1 ➜ Install spicetify
Copy this commands in the terminal:
```
curl -fsSL https://raw.githubusercontent.com/spicetify/spicetify-cli/master/install.sh | sh
 curl -fsSL https://raw.githubusercontent.com/spicetify/spicetify-marketplace/main/resources/install.sh | sh
 ```

## Step 2 ➜ Create config.ini file
To create the config.ini file, type in the terminal this command:
```
spicetify
```

## Step 3 ➜ Modify the spotify path and the prefs path
In the config.ini file, you need to specify the path to spotify and prefs.
- If you have spotify installed from Snap, is not going to work, so reinstall it from flathub.

Usually the path to spotify as flatpak is this:
```
/var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify/
```

For the refs file, check those two paths and copy the file location to the prefs file:
```
- ~/.config/spotify/prefs
```
```
- ~/.var/app/com.spotify.Client/config/spotify/prefs
```

## Step 4 ➜ Add permissions
Easy step, just execute this commands:
```
sudo chmod a+wr /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify
sudo chmod a+wr -R /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify/Apps
```

## Step 5 ➜ Choose a theme
Visit the page:

[Spicetify Themes GitHub](https://github.com/spicetify/spicetify-themes)

## Step 6 ➜ Add theme repo
First and foremost, let's backup spotify.
Run the command:
```
spicetify backup
```

Now, copy and paste those commands in the terminal to copy the repos for the themes:
```
git clone --depth=1 https://github.com/spicetify/spicetify-themes.git 
```

And copy the repo in the Spicetify folder:
```
cd spicetify-themes
cp -r * ~/.config/spicetify/Themes
```

## Step 7 Add theme to spotify
Finaly, let's add the theme we choose to spotify. I recommend to close spotify during this process.<br>
In my case, I'm going to use the Dribbblish theme with the Nord-Dark color scheme, to match my overall theme.<br>
First, let's add the theme. The themes name are the bigger one in the [THEMES.md](https://github.com/spicetify/spicetify-themes/blob/master/THEMES.md) file.<br>
Some of theme have color scheme, other don't.
To add the theme use this command:
```
spicetify config current_theme THEME_NAME
```

To change the color scheme in case you want to and it's available, run this command:
```
spicetify config color_scheme SCHEME_NAME
```

### And here it is, your spotify has a new theme!!
