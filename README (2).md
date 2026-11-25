# CareLoop Clinics --- Appointment No-Show Analysis

## Summary

-   **Part 1:** After cleaning, we had **990 appointments** to analyse.
    **218** were no-shows, giving an overall no-show rate of **22.02%**.
-   **Part 2:** Among clinics with at least **95 appointments**,
    Hadapsar Care Centre had the highest no-show rate at **27.3%**.
    Gomti Nagar's rate was **33.3%**, but it had only **90
    appointments**.
-   **Part 3:** Our Logistic Regression model achieved a **0.789
    ROC-AUC**. Using a **0.35 threshold**, it flagged **49 of the 198**
    test appointments for follow-up.
-   **Part 4:** We analysed **10 follow-up notes**: **5** were linked to
    appointments with a reminder recorded and **5** to appointments
    without one. This small sample is useful for illustration, but not
    enough to draw clinic-wide conclusions.

## Recommendation

CareLoop should use the model to help staff decide which patients to
call first, rather than treating its predictions as final decisions. In
the cleaned data, **218 of 990 appointments** were missed (**22.02%**).
No-shows were more common for appointments booked further ahead: the
rate was **30.0%** for bookings made **15--30 days** in advance and
**60.5%** for bookings made **31 or more days** ahead. This makes
earlier bookings a useful group to focus on when testing reminder
strategies. Hadapsar Care Centre had a **27.3%** no-show rate across
**143 appointments**, while Gomti Nagar Care Point had a higher rate of
**33.3%** but only **90 appointments**, below the reporting cutoff. The
model's **0.789 ROC-AUC** suggests it can help rank appointments by
risk. At the **0.35 threshold**, it flagged **49 of 198** test
appointments. CareLoop could start with a small pilot, track whether the
calls help patients attend, and adjust the threshold to fit the team's
call capacity.

## Model choice

We chose **Logistic Regression** because it gives understandable risk
estimates and achieved a **ROC-AUC of 0.789**. We used a **0.35
threshold** to flag appointments for follow-up. This is a starting point
for prioritizing calls---not a guarantee that a patient will miss an
appointment---and it should be adjusted based on staff capacity.

## Limitations

1.  The **10 notes** are only an illustration and cannot show the real
    reasons for no-shows across all clinics.
2.  The data split is random, so it does not test how well the model
    would perform on future appointments.
3.  The data are observational, so the patterns we found do not prove
    that one factor caused a patient to miss an appointment.
