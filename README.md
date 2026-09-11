===============================================
 THE HONORED ONE - AUTO CALAMITY RAID v2.6
===============================================

REQUIREMENTS
------------
  !! You need a move that lets you teleport with E (Shadow Step etc.) !!

  Any Cursed Technique works as long as you can enter the blue
  waiting circle with E. Shadow Step / True Six Eyes is the
  recommended setup, but the launcher lets you pick your CT and
  which ability keys to spam.

  !! Roblox MUST be snapped to the LEFT HALF of your screen !!

  The macro is built for half-screen Roblox only.
  Snap your Roblox window to the LEFT side before running.
  Do NOT run Roblox fullscreen — it will not work.


WHAT IT DOES
------------
  1. Optionally clicks the Return button to reset position at hub.
  2. Opens the map and locates The Honored One icon automatically
     using multi-scale template matching (works across zoom levels).
  3. Clicks The Honored One to open the detail panel, then hits
     Teleport. Verifies the panel appeared before proceeding.
  4. Waits for the game to load, then presses F at the structure.
  5. Clicks Calamity -> Create to start a raid lobby.
  6. Holds A for 0.5s to position, then holds S for up to 1.5s
     while scanning for the blue waiting circle using CV.
     Stops moving the instant the circle is detected.
  7. Detects the circle center using:
       - Strict HSV contour detection (bright cyan geometry)
       - 4-template fallback (circle, circle_close, circle_v2,
         circle_far) with subpixel refinement
       - Image moment centroid for accurate center calculation
  8. Moves the mouse to the circle center, right-clicks and
     presses E to teleport in using Shadow Step.
  9. Waits for the "Starting in" countdown or boss bar.
  10. Spams your selected ability keys in a loop until the raid ends.
      Domain/T fires on a 30s interval if enabled.
      Ten Shadows fires Y x3 at end-of-raid.
  11. Detects hub (raid ended) with 5 confirmations to avoid
      false positives during transitions.
  12. Repeats from step 1. If a cycle fails, the character is
      reset (ESC -> R -> Enter) before retrying.


CONSOLE TITLE BAR
-----------------
  The CMD window title bar shows live raid stats at all times:

    THE HONORED ONE  |  Raids: 4  |  Last: 62s  |  Session: 00:08:34

  This updates every second and is never cleared by the log wipe.


CONTROLS
--------
  F6 = Start / Pause
  F7 = Emergency Stop
  F9 = Print mouse coordinates to console


HOW TO SET UP
-------------
  STEP 1 — Run the launcher FIRST (launcher.py or Setup_and_Run.bat):

    launcher.py

  The launcher opens a settings window. Pick your resolution and
  hit SAVE & LAUNCH. It writes a settings.cfg file that the macro
  reads on startup. Your settings are saved and restored next time
  you open the launcher.

  STEP 2 — The launcher will start the macro automatically after saving.
  You can also run it directly:

    honored_one_macro_v6_3.py   (or use Run_Macro.bat)


LAUNCHER OPTIONS
----------------
  Resolution
    Pick your total desktop resolution. The macro scales all
    click regions automatically for your screen.

  👁 Preview Regions
    Draws coloured boxes on your screen showing exactly where
    the macro will search for each element. Click the overlay
    to close it. Use this to verify regions are correct before
    running.

  Cursed Technique
    Select your CT. Selecting Ten Shadows automatically enables
    the Y key and fires it 3x at the end of each raid.

  Attacks
    Toggle which ability keys to include in the combat rotation.
    Enabled keys: Z, V, F, C, X, R by default.
    T (Domain) is off by default — enable it if you have Domain.
    Y is controlled by the Ten Shadows toggle.

  Mouse Clicks
    Enter exact pixel coordinates for each click target.
    Use F9 in the macro to get coordinates while hovering.
    Leave as 0 to use automatic template matching instead.

  Advanced Settings
    VECTOR_ALPHA        -- Circle tracking smoothing (default 0.58)
                           Lower = more responsive, Higher = smoother
    RAID_START_TIMEOUT  -- Seconds to wait for boss bar (default 75)
    Threshold : honored -- Match confidence for Honored One icon
    Threshold : boss    -- Match confidence for boss bar
    Threshold : hub     -- Match confidence for hub detection
    Mask top %          -- Top boundary for circle HSV detection
    Mask bottom %       -- Bottom boundary for circle HSV detection
    Fallback top %      -- Top boundary for template fallback search
    Fallback bottom %   -- Bottom boundary for template fallback search

  Only touch Advanced Settings if the macro is missing detections
  or firing on wrong things. Defaults work for most setups.


SETTING IT UP FOR YOUR SCREEN
------------------------------
  !! YOU MUST RETAKE ALL TEMPLATE IMAGES ON YOUR OWN GAME !!

  The .png files included were captured on the original setup.
  They will NOT match your game if your resolution, graphics
  settings or UI scale is different.

  HOW TO RETAKE:
    1. Delete all existing .png files from the folder.
    2. Open Roblox and load into JJZ on your account.
    3. Snap Roblox to the LEFT HALF of your screen.
    4. Navigate to each relevant screen in your game.
    5. Use Snipping Tool (Win + Shift + S) to crop tightly
       around each element listed below.
    6. Save with the EXACT same filename.

  FILES TO RETAKE:
    honored_sword_new.png       -- The Honored One icon on the map
    honored_sword_selected.png  -- The Honored One icon when selected
    teleport_button_new.png     -- The Teleport button in the map panel
    calamity_button.png         -- The Calamity raid option button
    create_button.png           -- The Create button in the raid menu
    hub_buttons.png             -- Hub UI buttons (detects raid end)
    boss_bar.png                -- Boss health bar (detects raid start)
    blue_raid_circle.png        -- The blue waiting circle
    blue_raid_circle_close.png  -- Circle from close up
    blue_raid_circle_v2.png     -- Alternative circle angle/lighting
    blue_raid_circle_far.png    -- Circle from far away
    starting_in_text.png        -- The "Starting in" countdown text

  Crop each image as tightly as possible around the element.
  Loose crops with extra background reduce match accuracy.


TROUBLESHOOTING
---------------
  Macro not finding The Honored One on the map:
    -> Retake honored_sword_new.png on your game.
    -> Use 👁 Preview Regions in the launcher to check the
       search area covers your map correctly.

  Macro not clicking Teleport:
    -> Retake teleport_button_new.png.
    -> Or set exact click coordinates in Mouse Clicks section.

  Macro not entering the blue circle:
    -> Retake all four blue_raid_circle*.png files.
    -> Make sure Roblox is snapped to the LEFT HALF.
    -> Use 👁 Preview Regions to check the circle search area.

  Macro not detecting raid start / end:
    -> Retake boss_bar.png and hub_buttons.png.

  Everything looks right but nothing matches:
    -> Retake ALL the images. Delete every .png, retake them
       all on your own game, save with exact same filenames.

  Wrong resolution / coords:
    -> Run launcher.py again and pick the correct resolution.
       Make sure Roblox is snapped LEFT HALF before launching.

  Stats not showing in title bar:
    -> Make sure you are running via CMD or the .bat file.
       PowerShell / some terminals may not support title updates.


REQUIREMENTS.TXT
----------------
  Install dependencies with:
    pip install -r requirements.txt

  Or just run Setup_and_Run.bat — it installs everything automatically.
