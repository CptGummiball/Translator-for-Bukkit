# Readme

The `Translator` class is a lightweight utility for handling language translations in Bukkit/Spigot plugins. It allows developers to easily manage and retrieve translated messages from YAML files.

## Usage

1.  **Initialization**: Obtain an instance of the `Translator` using the `getInstance()` method.

```
Translator translator = Translator.getInstance();
``` 
    
3.  **Loading Languages**: Load language configurations during plugin initialization by calling the `loadLanguages(JavaPlugin plugin)` method, passing the main plugin instance.

```    
translator.loadLanguages(yourPluginInstance);
```
    
This method loads language configurations from YAML files located in the "translations" directory within your plugin's resources. The default language is set in the plugin's configuration file.
    
4.  **Translation**: Retrieve translated messages using the `translate(String key)` method.
   
``` 
String translatedMessage = translator.translate("example.key");` 
```
This method looks for the specified key in the language configuration corresponding to the chosen language in the config.yml. If the key is not found, it defaults to English ("en").
    

## Example



**Assuming 'yourPluginInstance' is your main plugin class:**
```
Translator translator = Translator.getInstance();
translator.loadLanguages(yourPluginInstance);
```
**Example translation usage:**
```
String playerName = "John";
String welcomeMessage = translator.translate("welcome.message")
.replace("%player%", playerName);
player.sendMessage(welcomeMessage);
```


## Configuration

To add or modify translations, create YAML files for each language in the "translations" directory. Use the following structure:

**translations/en.yml:**

    example:
      key: "This is an example message"
    welcome:
      message: "&aWelcome, %player%! &7Enjoy your stay."


## Notes

-   The default language is set in the plugin's configuration file.
-   Ensure that translation files follow the YAML format and are placed in the "translations" directory within your resources.
-   You can use Color Codes with `&`. For Example `&a` is green. [Minecraft-Color-Codes](https://htmlcolorcodes.com/minecraft-color-codes/)

Feel free to customize this class according to your plugin's requirements. Happy coding!
