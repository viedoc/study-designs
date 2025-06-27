# RTSM case: Dose finding

## Case
This is an example of a blinded study using logistics in which subjects are randomized to either “active” or “placebo” and were the subject can change kit type during the study. Subjects can at events after the first one change the dose of the treatment. At visit 1 the subject starts at dose 1, at visit 2 the subject can either stay on the same dose or step up to dose 2, at visit 3 the subject can stay on the same dose, step down to dose 1 or step up to dose 3. The example here is based on that there are distinct boxes at the site with kits for the different doses. For example the box for dose 1 contains both “active” and “placebo” kits only used for dose 1. This means that there are 3 different kinds of placebo kits and 3 kinds of active kits. And a total of 6 treatments/kit types. 

## Randomization form design
For this case there are three treatment fields “Dose 1”, “Dose 2”, and “Dose 3”. All have two treatment options, one for active and once for placebo. However, these are not the same exact treatments due to the difference in dose. For “Dose 1” the options are “Active 50mg” and “Placebo 50mg”, they have the codes 1 and 4, respectively. For “Dose 2” the options are “Active 100mg” and “Placebo 100mg”, they have the codes 2 and 5, respectively. For “Dose 3” the options are “Active 150mg” and “Placebo 150mg”, they have the codes 3 and 6, respectively. 

## Kit form design
The kit form is a simple example containing just a field for kit number and one for expiry date.

## Dose selection form
A special form here is the “dose selection” form. In this example it is a placeholder form. In a real study it may be called something else or be a checklist type form for safety or similar that determines which should be the next dose. The “dose selection” form here is an example to illustrate that there needs to be a form that governs the visibility of activities in events. These activities contain an allocation form and that there are more than one is due to that there are more than one kit type that can be allocated at visits and only one kit type can be selected for an activity.

## Study workflow settings
Randomization is performed at the first visit for which there is also a kit allocation form for “Dose 1”. At visit 2 there is one dose selection form described earlier. Depending on the answer in this form one of two activities is shown. One for allocating a “Dose 1” kit and one for allocating a “Dose 2” kit. At visit 3 there is again a dose selection form and depending on the answer in that form one of three activities is shown. One for allocating a “Dose 1” kit, one for allocating a “Dose 2” kit, and one for allocating a “Dose 3” kit.

## RTSM settings in designer
The three treatment fields are used as blinded outcome in the randomization. Then there are allocation properties. One input for treatment and two outputs, one for kit number the other for expiry date. For the advanced allocation the two blinded treatment fields are used to define what treatment should be allocated at specific events. In this case for Visit 1 there is only one allocation possible and that is for “Dose 1” so for this the “Dose 1” field is used. For Visit 2 there is an allocation of either dose 1 or dose 2, so for this visit there are two activities and thus two allocations. One for “Dose 1” for which the “Dose 1” field is used as treatment input, and one for “Dose 2” for which the “Dose 2” field is used as treatment input. For visit 3 there are three possibilities, so three activities each with their own allocation configuration. For “Dose 1” the “Dose 1” field is used, for “Dose 2” the “Dose 2” field, and for “Dose 3” the “Dose 3” field.

## RTSM settings in admin
For RTSM settings in admin select global list and enable logistics. For the randomization select the scope (e.g. “study”), all outputs are preset, then use static randomization method, confirm the settings, and upload the list.  The list will contain three columns for the three “Dose” fields. For “Dose 1” the list is randomized like in a normal static list randomization. And in this case contains code “1” (for active 50mg) or “4” (for placebo 50mg). In the columns for “Dose 2” and “Dose 3” you add the corresponding treatment as in the “Dose 1” column. So if it was “active” the code “2” for “Dose 2” and code “3” for “Dose 3”, and similarly if “placebo” code “5” for “Dose 2” and code “6” for “Dose 3”. The result is that for each row it is the same treatment but different treatment dose/kit types in the columns.
For the global allocation list select the scope (“site” if kits should only be allocated form the site stock). Then add the properties and settings like in the image below. The codes for treatments needs to be the same as in the design. In this case “1” for “Active 50mg”, “2” for “Active 100mg”, “3” for “Active 150mg”, “4” for “Placebo 50mg”, “5” for “Placebo 100mg”, and “6” for “Placebo 150mg”.

![image](https://github.com/user-attachments/assets/45ea026b-f964-46fe-9fa3-3328ade66736)

Then map the input and output properties like the image below. And then upload the list. The list only contains the treatment, kit numbers, and expiry date. For this example the first digit signifies dose level. It is used here for illustrative purposes but is not necessary.

![image](https://github.com/user-attachments/assets/207186ee-c48a-4dbf-8c83-4e9f14597a8d)
