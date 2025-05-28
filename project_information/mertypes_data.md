Subject: Data Discussion – Machines Error Database Export
Here is the data discussed today for two machines: WeTransfer link.
This is an SQL export of the error database stored locally on the machine. It is an event database where error or warning events are recorded along with their occurrence timestamp. The structure of this table is somewhat complex, but I will try to explain it.

    Each event has a MerNumber, which describes the error, and a MerDate, which represents the timestamp of occurrence.
    The attached PDF "Grader Errors and Warnings" provides details on all errors.
    MerNumber ≥ 400 indicates a lane error, while MerNumber < 400 represents a machine error.
    MerType specifies whether the error occurs (code 21 or 22) or when the error is resolved (code 23 or 24).
    There are other MerType values—refer to the "Grader Performance Calculation" PDF for an explanation of these fields.
    MerType 8 represents a message related to the machine stopping or starting, including the reason for the stop.
    Lane Pressure Control should contain the lane number that caused the machine to stop.
    MerSubnumber indicates the lane number where the issue occurred if MerNumber ≥ 400.
    MerSubnumber may have a different meaning if MerNumber < 400.
    MerData1, MerData2, MerData3, MerData4 provide additional information about the error.

The machines have the following number of lanes:

    Machine 16926: 16 lanes
    Machine 16589: 18 lanes

I have also added a new data export covering January 1st – February 24th to the ZIP file. Around week 7, a software update was performed, accidentally resetting all counters to zero.


Machine stop merTypr 8 > reason for stop pressure control (96) lane 18 > reason for pressure control lane 18 is because of a lot of reroutes (98) > reason for the (98) are the lane stops > which are mostly 490,411,453,414,460,452 > mostly lane 12