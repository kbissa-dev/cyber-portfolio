# JSON Field Guide

This file explains the fields used in `sample_scenarios.json`.

## id
A unique label for each scenario.

Examples:
- `PH-001` = phishing scenario
- `VG-001` = vishing scenario
- `LG-001` = legitimate scenario

## title
A short name for the scenario.

Example:
`Payroll portal password reset`

## type
The category of the scenario.

Values used in this project:
- `phishing`
- `vishing`
- `legitimate`

## channel
Where the scenario happens.

Examples:
- `email`
- `phone`
- `sms/email`

## scenario_text
A short explanation of what happens in the scenario.

This is the main situation being analysed.

## attacker_goal
What the attacker is trying to get.

Examples:
- login credentials
- payment details
- MFA code
- personal information
- remote access

## red_flags
A list of warning signs seen in the scenario.

Examples:
- urgency
- authority
- fear
- suspicious link
- payment request

## why_someone_might_trust_it
Explains why a normal person may believe the message or call.

This helps me think about the human side of social engineering.

## risk_level
A simple risk label for the scenario.

Current values:
- `High`
- `Low`

## recommended_action
The safest response to the scenario.

Examples:
- do not click the link
- do not share the code
- verify through an official channel
- report the message or call