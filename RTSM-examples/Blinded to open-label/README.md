# Read Me: Blinded to open-label RTMS

## Example case
This is an example of a blinded study using logistics that has two phases. One phase that is blinded and where the subject is randomized to either “active” or “placebo”, and then after the blinded phase subject move over to an open-label phase where all subjects receive “active”.

## Randomization form design
For this case there are two treatment fields “Treatment (Blinded)” and “Treatment (Open-label)”. The first have both treatments as option, the second only have “active”. Please note that “active” in both treatment fields use the same code value “1”.

## Kit form design
The kit form is a simple example containing just a field for kit number and one for expiry date.

## RTSM settings in designer
The two treatment fields are used as blinded outcome in the randomization. Then there are allocation properties. One input for treatment and two outputs, one for kit number the other for expiry date. For the advanced allocation the two blinded treatment fields are used to define which treatment should be allocated at specific events. For events that belong to the blinded phase the field “Treatment (Blinded)” is used as the treatment input. For events that belong to the open-label phase the field “Treatment (Open-label)” is used as treatment input.

## RTSM settings in admin
For RTSM settings in admin select global list and enable logistics.
For the randomization select the scope (e.g. “study”), all outputs are preset, then use static randomization method, confirm the settings, and upload the list. The list contains a column for each treatment field. For the one that is for the blinded phase treatment codes are added in a random order just like normal when using a static list randomization. The column for the open-label field should only contain the code for “active”.
For the global allocation list select the scope (“site” if kits should only be allocated form the site stock). Then add the properties and settings like in the image below. The codes for treatments needs to be the same as in the design. In this case “1” for “Active” and “2” for “Placebo”.

![image](https://github.com/user-attachments/assets/ef451646-f87c-4c99-bf08-ebeee7e3138d)

Then map the input and output properties like the image below. And then upload the list. The list only contains the treatment, kit numbers, and expiry date. 

![image](https://github.com/user-attachments/assets/a5ab33a4-c395-49c8-a9e6-90656d4c7895)
