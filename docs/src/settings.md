# Settings

To customize the settings, use the command from the Sublime menu:

    Preferences > Package Settings > Rust Enhanced > Settings - User

This should open a window that shows the default settings along with a description of each one.
This also has a view on the right-hand side to edit the settings which will be stored in `Packages/User/RustEnhanced.sublime-settings`.
These settings will apply globally across all Sublime windows and projects.

## Message display

See the [Diagnostic Messages](build/message.md) chapter for a description of the settings related to displaying diagnostic messages (warnings and errors generated by the compiler).

## Build settings

The build system can be configured with the `"cargo_build"` setting.
See the [Build Settings](build/settings.md) chapter for a description of these settings and how to configure them.

## On-save settings

The on-save checking settings are described in the [On-save checking](on-save.md#on-save-settings) chapter.

## Project-specific settings

You can customize settings per-project by adding settings to your `.sublime-project` file under the `"settings"` key.
For example, if you want to use Clippy as your default for [on-save checking](on-save.md) in just one project, something like the following can be added to your `.sublime-project` file:

```javascript
{
    // These are the folders opened in the project.
    "folders": [
        { "path": "." }
    ],
    // Any Sublime settings can go here, including Rust Enhanced settings.
    "settings": {
        // Changes the default on-save checking behavior to use Clippy.
        "rust_syntax_checking_method": "clippy",
    }
}
```