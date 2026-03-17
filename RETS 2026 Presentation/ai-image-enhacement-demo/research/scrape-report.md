# Listing Scrape Report

**Source:** https://www.propertybook.co.zw/listings/to-rent/3-bedroom-townhouse-cluster-waterfalls-harare-lzb0107
**Scraped:** 2026-03-13T03:16:54.164715
**Project:** `projects/listing-waterfalls-3bed-townhouse/`

---

## Listing Details

| Field | Value |
|-------|-------|
| Title | 3 Bedroom Townhouse/Cluster to Rent in Waterfalls |
| Price | USD 800 |
| Location | View Map |
| Bedrooms | 3 |
| Bathrooms | 2 |
| Garage Cars | 1 |

## Description (from listing)

> Townhouse living in Waterfalls along Masotchs WayNeat 3 bedroom townhouse within a secured complex offering privacy, convenience and easy living.It features fitted kitchen, open plan dining and lounge area and one main ensuite and a common bathroom. Direct access from the kitchen to the single lock-up garage.Additional benefits:5000L for reliable water supplyOvernight security ensuring peace of night sleep.An ideal option for those seeking comfortable low maintenance living in a well managed environment

## Features (from listing)

- BuyProperty for saleResidentialCommercialLandDevelopmentsOnShowNEW
- RentProperty to rentResidentialCommercialLand
- SellFind a Registered Estate AgentList Privately
- Developments
- OnShowNEW
- ResourcesBlogFind An AgentNeighbourhood GuidesPropertybook InsightsMortgage Calculator
- Contact Us
- List Property
- Login
- Sign Up
- Login

---

## Image Analysis (23 listing images)

_Excluded 3 non-listing images (map placeholder, site UI assets)._

| File | Room | Score | Lighting | Issues | Enhance? |
|------|------|-------|----------|--------|----------|
| listing-01.jpg | Exterior - Front of House | 6/10 | fair | Flat and dull lighting due to overcast conditions, Worn conc... | ⚠ YES |
| listing-02.jpg | exterior | 4/10 | good | Prominent watermark obstructing the view, Cracked and staine... | ⚠ YES |
| listing-03.webp | Exterior - Front of House | 6/10 | fair | Prominent and distracting watermark, Dull, overcast lighting... | ⚠ YES |
| listing-04.webp | kitchen | 7/10 | good | Prominent watermark obscures part of the image and is distra... | ⚠ YES |
| listing-05.webp | Open-plan living and kitchen area | 6/10 | good | Prominent watermark obstructing the view, Minor clutter on k... | ⚠ YES |
| listing-06.webp | Open-plan Kitchen, Dining, and Living Area | 3/10 | good | Prominent and distracting watermark covering central areas o... | ⚠ YES |
| listing-07.webp | kitchen | 6/10 | fair | image is slightly blurry/lacks sharpness, large, intrusive w... | ⚠ YES |
| listing-08.webp | Hallway | 4/10 | poor | Poor and uneven lighting, leading to a dim and uninviting at... | ⚠ YES |
| listing-09.webp | Utility Room | 6/10 | fair | Prominent watermark obstructing the view, Blown-out window w... | ⚠ YES |
| listing-10.webp | Bathroom | 4/10 | poor | Prominent watermark across the image, Poor lighting and unde... | ⚠ YES |
| listing-11.webp | Hallway/Entrance | 5/10 | fair | Prominent watermark obstructing the view, Dim and flat light... | ⚠ YES |
| listing-12.webp | Bedroom | 6/10 | fair | Prominent watermark covering a significant portion of the im... | ⚠ YES |
| listing-13.webp | bedroom | 4/10 | fair | Large, intrusive watermark covering the main subject, Clutte... | ⚠ YES |
| listing-14.webp | Bathroom | 6/10 | fair | Toilet lid is open, Toilet brush is visible, Prominent water... | ⚠ YES |
| listing-15.webp | unknown | 0/10 | — | — | ⚠ YES |
| listing-16.webp | bedroom | 7/10 | fair | Prominent watermark detracts from the image quality and prof... | ⚠ YES |
| listing-17.webp | Backyard/Outdoor Space | 4/10 | fair | Heavy obstruction by window frame, Watermark visible on main... | ⚠ YES |
| listing-18.webp | Bedroom | 3/10 | poor | Prominent watermark obstructing the view, Underexposed light... | ⚠ YES |
| listing-19.webp | Living Room | 6/10 | good | Watermark present on the image, Visible wires around the TV ... | ⚠ YES |
| listing-20.webp | Utility Room | 4/10 | fair | Prominent watermark obscuring details of the equipment, Clut... | ⚠ YES |
| listing-21.webp | Utility Room | 5/10 | fair | Distracting watermark, Blown-out window, Minor clutter on th... | ⚠ YES |
| listing-23.jpg | Exterior - Residential Development | 7/10 | good | Slight atmospheric haze, Could benefit from improved contras... | ⚠ YES |
| listing-24.webp | Exterior | 6/10 | fair | Prominent watermark obstructing the view of the house, Flat ... | ⚠ YES |

---

## Enhancement Queue (23 images)

Run these commands to generate AI-enhanced versions. **Review all AI images before using.**

### listing-01.jpg — Exterior - Front of House (6/10)

**Caption:** A front view of a single-story house featuring a beige roll-up garage door, a covered porch with sliding glass doors, and light brick accents. The property includes a small lawn and a paved driveway.
**Issues:** Flat and dull lighting due to overcast conditions, Worn concrete driveway and path, Satellite dish visible on the roof, Lack of vibrancy and contrast, Visible curtains behind the glass doors can make the interior look cluttered from the outside

```bash
bash scripts/generate-images.sh \
  "Enhance the image by brightening the overall exposure, increasing contrast and vibrancy to compensate for the overcast lighting. Improve the appearance of the lawn and concrete areas, and consider removing the satellite dish from the roof for a cleaner look. Adjust white balance to bring out more natural colors. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-01-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-01.jpg
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-02.jpg — exterior (4/10)

**Caption:** Front exterior view of a single-story brick house with a tiled roof, featuring a garage, a covered porch, and a paved walkway leading to the entrance. The property includes a well-maintained lawn.
**Issues:** Prominent watermark obstructing the view, Cracked and stained driveway, Overcast sky, which could be more appealing with a brighter blue

```bash
bash scripts/generate-images.sh \
  "Remove the prominent watermark from the center of the image. Repair cracks and stains on the driveway. Optionally, enhance the sky to a brighter, more appealing blue while maintaining natural lighting. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-02-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-02.jpg
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-03.webp — Exterior - Front of House (6/10)

**Caption:** A front exterior view of a single-story house, identified by the number 20, featuring a beige roll-up garage door on the left and a covered porch with brick pillars. The property includes a paved driveway leading to a small lawn area on the right, all under an overcast sky.
**Issues:** Prominent and distracting watermark, Dull, overcast lighting makes the property appear less inviting, Driveway concrete shows signs of wear and staining, Lack of vibrancy and contrast

```bash
bash scripts/generate-images.sh \
  "Remove the prominent watermark. Brighten the overall image, enhance colors and contrast to make the property appear more vibrant and inviting. Improve the appearance of the sky, potentially replacing it with a brighter, more appealing sky while maintaining realism. Clean up minor stains and wear on the driveway concrete. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-03-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-03.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-04.webp — kitchen (7/10)

**Caption:** A clean and well-equipped kitchen featuring modern black countertops, light-colored cabinetry, and essential appliances including a microwave, toaster, electric stove with oven, and an electric kettle.
**Issues:** Prominent watermark obscures part of the image and is distracting., Sticker on the oven door should be removed for a professional real estate photo., The composition is a bit tight, a slightly wider shot could better showcase the space.

```bash
bash scripts/generate-images.sh \
  "Remove the prominent watermark and the sticker from the oven door. Consider a slight adjustment to the crop to provide a bit more breathing room around the edges, if possible without distortion. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-04-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-04.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-05.webp — Open-plan living and kitchen area (6/10)

**Caption:** A functional open-plan living and kitchen area featuring a dining table, black leather sofas, and ample natural light. The space is practical but could benefit from updated styling and a clearer presentation.
**Issues:** Prominent watermark obstructing the view, Minor clutter on kitchen counter (blue tray), Pillows on sofa could be arranged more neatly for better staging, Slightly high camera angle makes the floor very prominent

```bash
bash scripts/generate-images.sh \
  "Remove the watermark 'Lizhibowa LZB0107 @obcloud'. Neatly arrange the pillows on the black leather sofas. Remove the blue tray from the kitchen counter. Adjust the perspective slightly to reduce the prominence of the floor and make the room feel more inviting. Enhance overall brightness and contrast for a professional look. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-05-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-05.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-06.webp — Open-plan Kitchen, Dining, and Living Area (3/10)

**Caption:** A functional open-plan space featuring a kitchen with white cabinetry and a black stove, a breakfast bar, a dining area with a wooden table, and a cozy living area with a sofa and television, all well-lit by natural and artificial light.
**Issues:** Prominent and distracting watermark covering central areas of the image, making it unsuitable for professional use., Could benefit from a slight overall brightness and color enhancement to appear more vibrant and inviting.

```bash
bash scripts/generate-images.sh \
  "Remove the prominent watermark 'Lizhibowa - LZB0107 © pbcloud' from the image. Slightly brighten the overall image and enhance color vibrancy to make the space more inviting, while maintaining a natural look. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-06-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-06.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-07.webp — kitchen (6/10)

**Caption:** A clean and functional kitchen featuring white upper and lower cabinets, a black countertop, and a dark refrigerator. The space offers practical storage solutions.
**Issues:** image is slightly blurry/lacks sharpness, large, intrusive watermark, composition is slightly angled/crooked, lack of professional staging

```bash
bash scripts/generate-images.sh \
  "Enhance the image by increasing sharpness and clarity, removing the watermark, straightening the perspective, and slightly brightening the overall scene to make it more inviting. Consider adding subtle staging elements like a fruit bowl or a small plant on the counter. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-07-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-07.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-08.webp — Hallway (4/10)

**Caption:** A dimly lit interior view of a hallway with a tiled floor, looking through a partially open door into another room. The image suffers from poor lighting, an awkward composition, and a prominent watermark, making it unappealing for real estate purposes.
**Issues:** Poor and uneven lighting, leading to a dim and uninviting atmosphere., Awkward composition with a low angle, a partially open door obscuring the view, and an object on the right cutting into the frame., Prominent and distracting watermark covering a significant portion of the image., Lack of a clear focal point or inviting perspective for a real estate photo.

```bash
bash scripts/generate-images.sh \
  "Significantly brighten the image, improve overall exposure and contrast, remove the prominent watermark, straighten the perspective, and crop slightly to improve composition by removing the distracting object on the right and focusing on the doorway and tiled floor. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-08-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-08.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-09.webp — Utility Room (6/10)

**Caption:** A utility room equipped with a solar power system, including an inverter, charge controller, and battery bank, alongside a washing machine. The room receives natural light, though the window is overexposed.
**Issues:** Prominent watermark obstructing the view, Blown-out window with no detail, Minor clutter on the floor to the left, Visible cables could be tidied for a cleaner aesthetic

```bash
bash scripts/generate-images.sh \
  "Remove the watermark 'Lizhibowa - LZB0107 © pbcloud'. Recover details in the blown-out window. Slightly brighten the overall image and enhance clarity. Remove the minor clutter on the floor to the left and tidy up visible cables for a cleaner presentation. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-09-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-09.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-10.webp — Bathroom (4/10)

**Caption:** This bathroom features a corner bathtub, a toilet, and a window providing natural light. The room is fully tiled and includes a small step for convenient access to the tub.
**Issues:** Prominent watermark across the image, Poor lighting and underexposure, with the window being overexposed, Toilet lid is open, which is generally not preferred in real estate photos, Door is partially open, cutting off the view, Some minor clutter (pink toilet brush, small mat), Dated aesthetic of tiles and fixtures

```bash
bash scripts/generate-images.sh \
  "Improve overall lighting and exposure, balancing highlights and shadows, especially around the window and in darker corners. Remove the prominent watermark. Close the toilet lid. Remove the pink toilet brush and the small mat. Slightly adjust the crop to better frame the main features. Enhance color vibrancy and sharpness. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-10-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-10.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-11.webp — Hallway/Entrance (5/10)

**Caption:** A view from a room looking into a tiled hallway through a partially open door, with a glimpse of a seating area on the right.
**Issues:** Prominent watermark obstructing the view, Dim and flat lighting, especially in the hallway, Awkward composition with cut-off furniture on the right, Lack of clear focal point, Some minor marks/discoloration on the wall

```bash
bash scripts/generate-images.sh \
  "Remove the large watermark. Brighten the overall image, particularly the hallway, to create a more inviting and well-lit atmosphere. Improve contrast and color vibrancy. Adjust the framing to either include more of the seating area or focus more clearly on the hallway entrance, avoiding awkward cut-offs. Clean up any visible wall marks. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-11-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-11.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-12.webp — Bedroom (6/10)

**Caption:** A tidy bedroom featuring a comfortable bed with a black upholstered headboard, neutral bedding, and full-length grey curtains. The room has a simple and functional design.
**Issues:** Prominent watermark covering a significant portion of the image, Overall lighting is a bit dim, making the room appear less inviting, Minor wrinkles visible on the bedding

```bash
bash scripts/generate-images.sh \
  "Remove the watermark 'Lizhibowa - LZB0107 © pbcloud' from the image. Brighten the overall image slightly to make the room appear more inviting, and gently enhance color vibrancy without over-saturating. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-12-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-12.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-13.webp — bedroom (4/10)

**Caption:** A bedroom featuring a comfortable bed with a striking blue headboard, a dressing table with a mirror, and a wall-mounted TV. The room has tiled flooring and curtains for privacy.
**Issues:** Large, intrusive watermark covering the main subject, Clutter on the floor near the dressing table (fan, wires, shoes), Room appears dim and lighting is uneven, Plastic wrapping still visible on the bed base, Visible marks/stains on the ceiling and upper walls, Slightly awkward framing, cutting off elements like the door frame and a nightstand

```bash
bash scripts/generate-images.sh \
  "Remove the large watermark. Brighten the overall image and improve lighting uniformity. Clean up the clutter on the floor near the dressing table. Remove the plastic wrapping from the bed base. Retouch any visible marks or stains on the ceiling and walls. Adjust framing slightly to be more balanced. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-13-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-13.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-14.webp — Bathroom (6/10)

**Caption:** A functional bathroom featuring a corner bathtub, toilet, and tiled walls, receiving natural light from a window.
**Issues:** Toilet lid is open, Toilet brush is visible, Prominent watermark obscures details, Door partially obstructs the view, Tiles appear somewhat dated

```bash
bash scripts/generate-images.sh \
  "Remove the prominent watermark, digitally close the toilet lid, remove the visible toilet brush, brighten the overall image, enhance contrast, and straighten the perspective for a more professional and appealing presentation. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-14-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-14.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-15.webp — unknown (0/10)

**Caption:** error
**Issues:** 

```bash
bash scripts/generate-images.sh \
  "Professional real estate photo, bright natural light, clean composition. Realistic, not a rendering. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-15-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-15.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-16.webp — bedroom (7/10)

**Caption:** A simple and tidy bedroom featuring a single bed with a grey tufted headboard, light-colored bedding, and a small two-drawer nightstand. Natural light filters through the patterned curtains, illuminating the space.
**Issues:** Prominent watermark detracts from the image quality and professionalism., Curtains appear slightly overexposed in areas due to strong backlighting., The overall color palette of the room (wall color) might be considered dated by some.

```bash
bash scripts/generate-images.sh \
  "Remove the watermark. Slightly brighten the overall image and balance the exposure, particularly on the curtains, to reduce any blown-out areas. Enhance color vibrancy subtly for a more inviting look. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-16-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-16.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-17.webp — Backyard/Outdoor Space (4/10)

**Caption:** A view of a gravel backyard featuring a large green water tank and a barbecue stand, seen through a window.
**Issues:** Heavy obstruction by window frame, Watermark visible on main subject, Blurry image quality, Clutter (mop/rag) visible in foreground, Uninviting gravel surface, Lack of professional staging

```bash
bash scripts/generate-images.sh \
  "Remove the window frame obstruction, remove the watermark, sharpen the image, remove the mop/rag from the bottom left, and enhance the overall clarity and brightness to make the backyard appear more inviting. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-17-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-17.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-18.webp — Bedroom (3/10)

**Caption:** A view of a built-in wooden wardrobe in a bedroom, featuring a light wood finish and modern handles. The room also includes a mirror and television on the right side.
**Issues:** Prominent watermark obstructing the view, Underexposed lighting, making the room appear dim and flat, Tilted perspective, causing the image to lean to the right, Visible clutter including wires and a fan on the right side of the room, Lack of vibrancy and contrast

```bash
bash scripts/generate-images.sh \
  "Remove the prominent watermark. Correct the tilted perspective. Brighten the overall image to improve exposure and make the space feel more inviting. Enhance color vibrancy and contrast. Remove visible clutter such as wires and the fan on the right side of the room. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-18-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-18.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-19.webp — Living Room (6/10)

**Caption:** A living room featuring a traditional fireplace with a modern television mounted above, and a glimpse into an adjacent hallway.
**Issues:** Watermark present on the image, Visible wires around the TV and fireplace, Sofa is cut off on the left side of the frame, Image appears slightly tilted, Some dust or marks visible on the fireplace surround

```bash
bash scripts/generate-images.sh \
  "Remove the watermark, clean up visible wires around the TV and fireplace, straighten the image to correct the slight tilt, and adjust the crop to better frame the living space, minimizing cut-off elements like the sofa. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-19-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-19.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-20.webp — Utility Room (4/10)

**Caption:** This image displays the home's solar power system, featuring a charge controller and inverter, highlighting an energy-efficient upgrade. The area could benefit from tidying for presentation.
**Issues:** Prominent watermark obscuring details of the equipment, Clutter (laundry basket) detracting from the main subject, Messy and exposed wiring, Lack of wider room context, Overall presentation is not appealing for a real estate listing

```bash
bash scripts/generate-images.sh \
  "Remove the watermark, clean up the visible wiring, remove the laundry basket, and slightly brighten the overall image to improve presentation for a real estate listing. Consider a wider shot to provide more room context. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-20-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-20.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-21.webp — Utility Room (5/10)

**Caption:** A functional utility room equipped with a washing machine and a comprehensive solar power system, including an inverter, charge controller, and a SAKO lithium battery power bank, suitable for off-grid or backup energy needs.
**Issues:** Distracting watermark, Blown-out window, Minor clutter on the floor and on top of the battery, Uneven lighting with some shadows, Lack of staging or aesthetic appeal for a real estate listing

```bash
bash scripts/generate-images.sh \
  "Remove the watermark, correct the blown-out window, brighten the shadows, remove the spray bottle and plastic bag from the top of the battery, and improve overall color balance and sharpness. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-21-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-21.webp
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-23.jpg — Exterior - Residential Development (7/10)

**Caption:** An expansive aerial view showcasing a mix of established residential neighborhoods and large undeveloped land plots, indicating potential for future growth and development.
**Issues:** Slight atmospheric haze, Could benefit from improved contrast and dynamic range

```bash
bash scripts/generate-images.sh \
  "Enhance sharpness and contrast, reduce atmospheric haze, and subtly boost color vibrancy to make the green spaces and residential areas more appealing. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-23-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-23.jpg
```
> ⚠ AI-ENHANCED — human approval required before use.

### listing-24.webp — Exterior (6/10)

**Caption:** A single-story brick house with a tiled roof, featuring a front porch and an attached garage. The property includes a well-maintained lawn and a paved walkway. The image was taken on an overcast day, and a large watermark obscures part of the facade.
**Issues:** Prominent watermark obstructing the view of the house, Flat and dull lighting due to overcast conditions, Cracked driveway visible on the left, Intrusive tree branch in the top right corner, Lack of vibrant colors and contrast

```bash
bash scripts/generate-images.sh \
  "Remove the prominent watermark 'izhibowa - LZB0107 @bbcloud'. Replace the overcast sky with a bright, clear blue sky. Enhance overall brightness, color vibrancy, and contrast. Sharpen details of the house and landscaping. Remove the cracked section of the driveway and the intrusive tree branch from the top right. Style: natural, bright, inviting real estate photography. Realistic, NOT a rendering." \
  projects/listing-waterfalls-3bed-townhouse/images/final/listing-24-enhanced.jpg \
  --ref projects/listing-waterfalls-3bed-townhouse/images/user/listing-24.webp
```
> ⚠ AI-ENHANCED — human approval required before use.


---

## Ready-to-Use Images (0 — score ≥ 7, no flag)

_None — all images flagged for enhancement._

---

## Next Steps

1. Review images in `projects/listing-waterfalls-3bed-townhouse/images/user/`
2. Run enhancement commands above — review all AI results
3. Copy approved images to `projects/listing-waterfalls-3bed-townhouse/images/final/`
4. Run area research (see commands below)
5. Build listing page per `docs/rules/11-real-estate-listing.md`

## Area Research Commands

```bash
bash scripts/serper-web.sh "Waterfalls suburb Harare Zimbabwe neighborhood guide"
bash scripts/serper-web.sh "Waterfalls Harare schools amenities shopping"
bash scripts/serper-web.sh "Waterfalls Harare property prices rent 2024 2025"
bash scripts/serper-web.sh "Waterfalls Harare safety security"
```

---

> ⚠ Do not add any claim not in the original listing or a verifiable source.
> ⚠ All AI-enhanced images must be labelled and human-approved before publishing.
