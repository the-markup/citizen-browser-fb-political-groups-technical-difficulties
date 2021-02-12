# Citizen Browser - Political Group Recommendations Technical Difficulties
This repository contains data to reproduce the findings featured in our story, "[Facebook Says 'Technical Issues' Were the Cause of Broken Promise to Congress](https://themarkup.org/citizen-browser/2021/02/12/facebook-says-technical-issues-were-the-cause-of-broken-promise-to-congress)" from our series, [Citizen Browser](https://themarkup.org/citizen-browser/).

Our methodology is described in "[Facebook Said It Would Stop Pushing Users to Join Partisan Political Groups. It Didn’t.](https://themarkup.org/citizen-browser/2021/01/19/facebook-said-it-would-stop-pushing-users-to-join-partisan-political-groups-it-didnt)" and "[How We Built a Facebook Inspector](https://themarkup.org/citizen-browser/2021/01/05/how-we-built-a-facebook-inspector)".

## data/
The `data/` directory contains several spreadsheets.

`political_group_recs_over_time.csv` contains the number of political groups recommended to Citizen Browser panelists daily from December 1st 2020 to February 10th 2021. We only count groups recommended to at least three panelists.<br>
`panelists_over_time.csv` contains the daily count of panels' data we collected.<br>
`political_group_recs.csv` contains granular data about political groups recommended over time.

| column              | description                                                                      |
|:--------------------|:---------------------------------------------------------------------------------|
| collection_datetime | The date the group was recommended to panelists.                                 |
| group_slug          | The unique identifier for the group. `https://facebook.com/groups/{group_slug}`  |
| n_user_recommend    | The number of panelists who were recommended this Facebook Group                 |
| group_name          | The name of the Facebook Group                                                   |
| n_members           | The max number of members in the Facebook Group during the `collection_datetime` |


`group_membership_growth.csv` contains the daily membership growth rates before and after January 19th, 2021.

| column                     | description                                                                                                                                                                                    |
|:---------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| group_slug                 | The unique identifier for the group. `https://facebook.com/groups/{group_slug}`                                                                                                                |
| group_name                 | The name of the Facebook Group                                                                                                                                                                 |
| n_members_Jan-19           | The number of members in the Facebook Group on Jan 19 This is from our data                                                                                                                    |
| n_members_Feb-11           | The number of members in the Facebook Group on Feb 11. This is from visiting "about" section of groups                                                                                         |
| users/day_Jan-19_to_Feb-11 | The number of daily net users that join or leave a group after Jan 19th. Derived from `n_members_Feb-11` - `n_members_Jan-19` / 22 days                                                        |
| users/day_Dec_to_Jan-19    | The number of daily net users that join or leave a group before Jan 19th. Derived from `n_members_Jan_19` - `n_members_Prior` / X days. The prior date is the earliest occurance for panelists |
| percent_change             | The percent change between daily membership changes before and after Jan 19th. `users/day_Jan-19_to_Feb-11` - `users/day_Dec_to_Jan-19` / `users/day_Dec_to_Jan-19`                            |

## Licensing
Copyright 2021, The Markup News Inc.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
