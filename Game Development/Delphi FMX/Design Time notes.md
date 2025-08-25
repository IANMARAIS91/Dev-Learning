To get the table view, use the following prompt:
Give me the markdown code for the recommended fmx elements & properties table


| Element / Property | Purpose | Notes |
|--------------------|---------|-------|
| **`TLayout`** | Acts as a scalable container for your image and all overlay items | Place your `TImage` inside it, then place all clickable/visual items as children of the same layout. Scaling the layout scales everything proportionally. |
| **`TImage`** | Displays your background image | Set `WrapMode := Stretch` or `Fit` depending on whether you want to preserve aspect ratio. |
| **`Align := Client`** on `TImage` | Makes the image fill the container | Ensures it always matches the layout’s size. |
| **Anchors** | Keeps relative positioning | If you want an item to stay in a corner or edge, set anchors accordingly. |
| **`TScaledLayout`** (FMX 10.4+) | Automatically scales child controls based on a base size | Perfect for DPI-aware designs and proportional scaling. |
| **`TImageControl`** | Alternative to `TImage` that can scale and clip content | Useful if you want zoom/pan features. |
| **`TImageCollection` + `TVirtualImage`** | For high-DPI, multi-resolution images | Ensures crisp visuals when scaling on different screens. |
| **`Scale` property** (on any control) | Manual proportional scaling | Can be set in code or design time to zoom in/out while keeping proportions. |
