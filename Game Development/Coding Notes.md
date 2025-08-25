FullScreen := True;
To activate a Fullscreen prompt

Fullscreen := false;
To deactivate a Fullscreen prompt

Fullscreen := not(Fullscreen);
To toggle between states

SectionTutorial.BringToFront;
When needing to switch to different screen when clicking button

SectionTutorial.Repaint;
To prevent MouseEntry & MouseLeave from moving the object from its intended position.

TLayout
Purpose: Acts as a scalable container for your image and all overlay items.
Place your TImage inside it, then place all clickable/visual items as children of the same layout. Scaling the layout scales everything proportionally.
Note