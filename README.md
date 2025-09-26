# Material You Home Assistant Dashboard

This repository contains the YAML configuration for a responsive, Material You-inspired dashboard for Home Assistant, with layouts for both tablet and mobile.

## ✨ Previews

### Tablet Version
![Dashboard Preview](/dashboards/IMG_0804.PNG)
![Dashboard Preview second page](/dashboards/IMG_0809.jpg)

### Mobile Version

![Mobile Dashboard Preview 1](/dashboards/IMG_1222.jpeg)
![Mobile Dashboard Preview 2](/dashboards/IMG_1226.jpeg)
![Mobile Dashboard Preview 3](/dashboards/IMG_1225.jpeg)


## How to Use

### 1. Install Prerequisites (Theme & Custom Cards)

First, install the required theme and custom cards from HACS.

#### Theme
* Copy the contents of the `material_you_gradient.yaml` file.
* In your Home Assistant configuration directory, find the `themes` folder. If it doesn't exist, create it.
* Inside the `themes` folder, create a new file named `material_you_gradient.yaml` and paste the contents into it.
* Go to your user profile in Home Assistant and select "Material You Gradient" as your theme.

#### Required Custom Cards
Install the following custom cards from the Home Assistant Community Store (HACS):
- `custom:timeflow-card`
- `custom:mushroom-template-card`
- `custom:mushroom-entity-card`
- `custom:swipe-card`
- `custom:button-card`
- `custom:gap-card`
- `custom:navbar-card`
- `custom:vertical-stack-in-card`
- `custom:mini-graph-card`

### 2. Choose and Create Your Dashboard

Now, copy the configuration for the dashboard version you want to create.

#### For the Tablet Version
* Copy the contents of the `dashboard.yaml` file.
* In Home Assistant, go to **Settings > Dashboards**.
* Click on **Add Dashboard** and give it a name (e.g., "Tablet Dashboard").
* Click on the three dots in the top right corner and select **Raw configuration editor**.
* Paste the contents of `dashboard.yaml` here and save.

#### For the Mobile Version
* Copy the contents of the `dashboard_mobile.yaml` file.
* In Home Assistant, go to **Settings > Dashboards**.
* Click on **Add Dashboard** and give it a name (e.g., "Mobile Dashboard").
* Click on the three dots in the top right corner and select **Raw configuration editor**.
* Paste the contents of `dashboard_mobile.yaml` here and save.

### 3. (Optional) Kiosk Mode

This dashboard looks best in a full-screen kiosk mode. To enable this, install the following from HACS:
- `Kiosk Mode`
- `browser_mod`

The dashboard expects an `input_boolean` entity to act as the toggle for kiosk mode. Create an `input_boolean` in your Home Assistant Helpers section and name it `Kiosk Mode`.

**Notes:**
- Use `browser_mod` to target specific browsers/devices (if you want kiosk mode only on your tablet). See the `browser_mod` documentation for the correct service calls for your version.

---

### 4. (Optional) Hide Navigation Bar

If you want to hide the top navigation bar, follow these steps:

1.  Create a new file named `my-custom-styles.css` inside your `/config/www/` folder.
2.  Paste the following code into the file and save it:
    ```css
    html {
      --navbar-display: none !important;
    }
    ```
3.  In Home Assistant, go to **Settings > Dashboards**, open the top-right three-dot menu, and select **Resources**.
4.  Click **+ Add Resource** and enter the following:
    * **URL**: `/local/my-custom-styles.css`
    * **Resource Type**: `Stylesheet (CSS)`
5.  Click **Create**, then go to your dashboard and perform a hard refresh (Ctrl+F5 or Cmd+Shift+R).

> [!TIP]  
> ## ✨ Small self promotion : `custom:timeflow-card`
> 
> If you like the dashboard, please check out my card **`custom:timeflow-card`**.  
> This card allows you to create **beautiful timers and countdowns**.
>
> In this dashboard, `timeflow-card` is used to:
> - **Track Alexa Timers** – Automatically picks up timers and displays them  
> - **Countdown to Events** – Visualize time remaining until sunrise, sunset, or your next backup using entities  
> - **Simple Timers** – Keep track of everyday timers, like for making tea ☕
>
> 🔗 For more info, check out the [Timeflow-Card](https://github.com/Rishi8078/TimeFlow-Card)

---

<a href="https://coff.ee/rishi8078" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 40 px !important;width: 144.666px !important;" ></a>