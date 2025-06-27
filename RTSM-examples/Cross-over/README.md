# RTMS case: Cross-over

## Case
This is an example of a blinded study using logistics that has a cross-over design. The subjects are randomized to either “active” or “placebo” for the first period, and then the other for the second period. 

## Randomization form design
For this case there are two treatment fields “Treatment – Period 1” and “Treatment – Period 2”. Both have the options “active” and “placebo”, and both use the same code values for the treatments.

## Kit form design
The kit form is a simple example containing just a field for kit number and one for expiry date.

## Study workflow settings
Randomization is performed at the first visit for which there is also a kit allocation form. For the subsequent visits there is only the allocation form.

## RTSM settings in designer
The two treatment fields are used as blinded outcome in the randomization. Then there are allocation properties. One input for treatment and two outputs, one for kit number the other for expiry date. For the advanced allocation the two blinded treatment fields are used to define what treatment should be allocated at specific events. For events that belong to Period 1 the field “Treatment – Period 1” is used as the treatment input. For events that belong to Period 2 the field “Treatment – Period 2” is used as treatment input.

## RTSM settings in admin
For RTSM settings in admin select global list and enable logistics.
For the randomization select the scope (e.g. “study”), all outputs are preset, then use static randomization method, confirm the settings, and upload the list. The list contains a column for each treatment field. For the one that is for Period 1 treatment codes are added in a random order just like normal when using a static list randomization. For the Period 2 treatment the code is the other compared to Period 1. For example if it is “1” (for active) for Period 1, then for Period 2 it should be “2” (for placebo).
For the global allocation list select the scope (“site” if kits should only be allocated form the site stock). Then add the properties and settings like in the image below. The codes for treatments need to be the same as in the design. In this case “1” for “Active” and “2” for “Placebo”.

![image](https://github.com/user-attachments/assets/1bb1621f-bdac-45e2-98e3-7ec98017e124)

Then map the input and output properties like the image below. And then upload the list. The list only contains the treatment, kit numbers, and expiry date. 

![image](https://github.com/user-attachments/assets/2da6d05b-1728-4ed9-b57a-18867f831093)

