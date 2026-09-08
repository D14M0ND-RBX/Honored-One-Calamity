===============================================
 THE HONORED ONE - AUTO CALAMITY RAID v2.1
===============================================
  Complete-Edition
===============================================

REQUIREMENTS
------------
  !! AWK LIMITLESS WITH SHADOW STEP / TRUE 6 EYES IS NEEDED !!

  As long as you have Shadow Step and can teleport with E,
  you can use any CT. Awakened Limitless with True Six Eyes
  is the recommended setup.

  !! Roblox MUST be snapped to the LEFT HALF of your screen !!

  The macro is designed for half-screen Roblox only.
  Snap your Roblox window to the LEFT side before running.
  Do NOT run Roblox fullscreen — it will not work correctly.


WHAT IT DOES
------------
  1. Opens the map and locates The Honored One icon.
  2. Clicks The Honored One and hits Teleport.
  3. Presses F to interact at the structure.
  4. Clicks Calamity -> Create to start a raid lobby.
  5. Detects the blue waiting circle using computer vision.
  6. Moves the mouse to the circle, right-clicks and presses E
     to teleport in using Shadow Step.
  7. Waits for the boss bar to appear (raid started).
  8. Spams abilities: R, F, X, C, V, Z in a loop (no T/Domain).
  9. Detects when the raid ends and you return to hub.
  10. Presses Y x3 and repeats from step 1.

  NOTE: T/Domain is disabled in this version.
        Use the Domain folder if you want Domain enabled.


HOW TO SET UP
-------------
  STEP 1 — Run the launcher FIRST (every time before the macro):

    launcher.py

  The launcher opens a settings window. Pick your resolution
  and hit SAVE & LAUNCH. It writes a settings.cfg file that
  the macro reads on startup.

  STEP 2 — Run the macro:

    honored_one_macro_v6_3.py   (or use Run_Macro.bat)

  The macro reads settings.cfg automatically. You do NOT need
  to edit the script itself.


CONTROLS
--------
  F6 = Start / Pause
  F7 = Emergency Stop
  F9 = Print mouse coordinates to console


SETTING IT UP FOR YOUR SCREEN
------------------------------
  !! YOU MUST RETAKE ALL THE TEMPLATE IMAGES ON YOUR OWN GAME !!

  The .png files included are screenshots from the original
  setup. They will NOT match your game if your resolution,
  graphics settings or UI scale is different.

  HOW TO RETAKE THE IMAGES:
    1. DELETE all the existing .png files from the folder first.
    2. Open Roblox and load into Jujutsu Zero on YOUR account.
    3. Snap Roblox to the LEFT HALF of your screen.
    4. Navigate to each relevant screen in your own game.
    5. Use Snipping Tool (Win + Shift + S) to crop tightly
       around each element listed below.
    6. Save each screenshot using the EXACT same filename.
       The macro will only work with images taken from YOUR game.

  FILES TO RETAKE:
    honored_sword_new.png       -- The Honored One icon on the map
    honored_sword_selected.png  -- The Honored One icon when selected
    teleport_button_new.png     -- The Teleport button in the map panel
    calamity_button.png         -- The Calamity raid option button
    create_button.png           -- The Create button in the raid menu
    hub_buttons.png             -- The hub UI buttons (to detect raid end)
    boss_bar.png                -- The boss health bar (to detect raid start)
    blue_raid_circle.png        -- The blue waiting circle on the ground
    blue_raid_circle_close.png  -- The circle from close up
    blue_raid_circle_v2.png     -- Alternative circle angle/lighting
    starting_in_text.png        -- The "Starting in" countdown text

  Crop each image as tightly as possible around the element.
  Loose crops with extra background will reduce match accuracy.


ADVANCED SETTINGS (launcher.py)
--------------------------------
  Click "Advanced Settings" in the launcher to tune:

    VECTOR_ALPHA        -- Smoothing for circle tracking (default 0.58)
                           Lower = more responsive, Higher = smoother
    RAID_START_TIMEOUT  -- Seconds to wait for boss bar (default 75)
    Threshold : honored -- Match confidence for Honored One icon
    Threshold : boss    -- Match confidence for boss bar
    Threshold : hub     -- Match confidence for hub detection
    Mask top %          -- How much of the top to ignore in circle detection
    Mask bottom %       -- How much of the bottom to ignore
    Fallback top %      -- Fallback detector search area top
    Fallback bottom %   -- Fallback detector search area bottom

  You only need to touch these if the macro is missing detections
  or firing incorrectly. Default values work for most setups.


TROUBLESHOOTING
---------------
  Macro not finding The Honored One on the map:
    -> Retake honored_sword_new.png on your game.

  Macro not clicking Teleport:
    -> Retake teleport_button_new.png on your game.

  Macro not entering the blue circle:
    -> Retake all three blue_raid_circle*.png files.
    -> Make sure Roblox is snapped to the LEFT HALF of screen.

  Macro not detecting raid start / end:
    -> Retake boss_bar.png and hub_buttons.png on your game.

  Everything looks right but nothing matches:
    -> You probably need to retake ALL the images.
       Delete every .png, retake them all on your own game,
       save with the exact same filenames.

  Wrong resolution / coords:
    -> Run launcher.py again and pick the correct resolution.
       Make sure Roblox is snapped LEFT HALF before launching.


REQUIREMENTS.TXT
----------------
  Install dependencies with:
    pip install -r requirements.txt
