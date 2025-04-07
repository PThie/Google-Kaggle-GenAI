# Documentation of Prompts and Settings

## Content

- [Execution-1](#execution-1)

## Template

<table>
    <tr>
        <td>Name</td>
        <td>...</td>
    </tr>
    <tr>
        <td>Goal</td>
        <td>...</td>
    </tr>
    <tr>
        <td>Model</td>
        <td>...</td>
    </tr>
    <tr>
        <td>Temperature</td>
        <td>...</td>
    </tr>
    <tr>
        <td>Top-K</td>
        <td>...</td>
    </tr>
    <tr>
        <td>Top-P</td>
        <td>...</td>
    </tr>
    <tr>
        <td>Token Limit</td>
        <td>...</td>
    </tr>
    <tr>
        <td>Prompt</td>
        <td>See below</td>
    </tr>
    <tr>
        <td>Output</td>
        <td>See below</td>
    </tr>
</table>

## Execution-2

<table>
    <tr>
        <td>Name</td>
        <td>Dramatic newspaper article JFK - with News API</td>
    </tr>
    <tr>
        <td>Goal</td>
        <td>Generating a better version of the newspaper by feeding in news article from Wikinews</td>
    </tr>
    <tr>
        <td>Model</td>
        <td>deepseek-r1-distill-llama-70b</td>
    </tr>
    <tr>
        <td>Temperature</td>
        <td>0.9</td>
    </tr>
    <tr>
        <td>Top-K</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Top-P</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Token Limit</td>
        <td>2000</td>
    </tr>
    <tr>
        <td>Prompt</td>
        <td>See below</td>
    </tr>
    <tr>
        <td>Output</td>
        <td>See below</td>
    </tr>
</table>

### Prompt Execution-2

```{python}
# inputs
event = "Assassination of John F Kennedy"
scenario = "What if JFK was not murdered?"
output_type = "news article"
role = "journalist"
additional_instructions = "Be dramatic. You are working for The Sun." # In case you want to give the text a specific twist. If not, leave empty!

prompt = f"""
    Based on the following Wikipedia summary about the {event}:
    {getting_background_wikipedia(event)}
    Further, here some relevant news article from the past: {getting_wikinews(event)}
    Take on the role {role} in 2025. Write a {output_type}.
    Imagining that the following event in history had a different outcome: {event}.
    Consider the following scenario: {scenario} as counterfactual scenario.
    {additional_instructions}
    Write it not conditional. Write in active style such that you could think it really happened like this
"""
```

### Output Execution-2

📰 JFK SURVIVES DALLAS SHOT: A PRESIDENT'S MIRACLE AND A NATION REBORN



*Dallas, TX — November 22, 1963* — In a stunning turn of events that will be etched into
the annals of American history, President John F. Kennedy has survived the assassination
attempt in Dallas, Texas. The nation, left breathless and in disbelief, is grappling with
the magnitude of what could have been—and what now can be.



At approximately 12:30 p.m. Central Standard Time, as Kennedy’s motorcade made its way
through Dealey Plaza, shots rang out from the sixth floor of the Texas School Book
Depository. The President was struck in the neck, but in a miraculous twist, the wound was
not fatal. Texas Governor John Connally, who was riding alongside Kennedy, was also
injured but is expected to recover.



Secret Service agents acted with lightning speed, rushing the presidential limousine to
Parkland Memorial Hospital. Doctors worked tirelessly to stabilize Kennedy, who underwent
emergency surgery. By evening, the President was listed in stable condition, his trademark
charm and resilience already shining through. “He gave us a thumbs-up from the gurney,”
said one hospital source, who spoke on condition of anonymity. “It’s JFK being JFK.”



The would-be assassin, Lee Harvey Oswald, a 24-year-old former Marine and employee of the
depository, was apprehended by Dallas police just 70 minutes after the shooting. Oswald,
who had a history of radical leanings and defected to the Soviet Union in 1959, was found
hiding in the Texas Theatre, a local movie house. A scuffle ensued, and Oswald was subdued
after pulling a revolver and firing at an officer. “He didn’t go down without a fight,”
said one officer involved in the arrest.



The nation held its breath as details of the failed assassination trickled out. Jacqueline
Kennedy, who cradled her husband’s head in her lap during the chaotic ride to the
hospital, emerged as a symbol of strength. “She was calm, almost serene,” said a Secret
Service agent. “She kept saying, ‘He’s going to be okay.’ And somehow, you believed her.”



As the hours passed, the country erupted in a mix of relief and outrage. Church bells
tolled in every state, and impromptu vigils popped up from Times Square to the Golden Gate
Bridge. In Washington, Vice President Lyndon B. Johnson, who had been riding in a car
behind Kennedy, was visibly shaken but vowed, “We will not let this act of violence define
us. We will move forward, together.”



The FBI, under the direction of J. Edgar Hoover, has taken over the investigation, with
Attorney General Robert F. Kennedy leading the charge. “We will leave no stone unturned,”
RFK declared. “The American people deserve answers, and they deserve justice.” Early
evidence suggests Oswald acted alone, but theories are already swirling about possible
wider conspiracies.



As the President begins his recovery, the question on everyone’s mind is: *What now?*
Kennedy’s survival has sent shockwaves through the political landscape. His aides are
already whispering about a renewed push for civil rights legislation, which had stalled in
Congress. “This was a wake-up call,” said one White House insider. “The President is more
determined than ever to see his vision for America through.”



Historians are already calling this a turning point in the Kennedy presidency. “If he can
survive this, there’s no limit to what he can achieve,” said presidential historian Arthur
M. Schlesinger Jr. “This is a second chance—not just for JFK, but for the country.”



As the sun sets on Dallas, the mood is one of cautious optimism. The Kennedys, ever the
embodiment of hope, have once again reminded America of its resilience. And as the
President recuperates, the nation is left to ponder the infinite possibilities of a future
that very nearly wasn’t.



*In a world that came too close to losing its leader, the words of John F. Kennedy himself
ring truer than ever: “Let every nation know, whether it wishes us well or ill, that we
shall pay any price, bear any burden, meet any hardship, support any friend, oppose any
foe to assure the survival and the success of liberty.”*




📰 Byline: Emily J. Miller, National Affairs Correspondent, The Sun

## Execution-1

<table>
    <tr>
        <td>Name</td>
        <td>Dramatic News JFK</td>
    </tr>
    <tr>
        <td>Goal</td>
        <td>Producing dramatic news article on assassination of JFK</td>
    </tr>
    <tr>
        <td>Model</td>
        <td>deepseek-r1-distill-llama-70b</td>
    </tr>
    <tr>
        <td>Temperature</td>
        <td>0.9</td>
    </tr>
    <tr>
        <td>Top-K</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Top-P</td>
        <td>-</td>
    </tr>
    <tr>
        <td>Token Limit</td>
        <td>2000</td>
    </tr>
    <tr>
        <td>Prompt</td>
        <td>See below</td>
    </tr>
    <tr>
        <td>Output</td>
        <td>See below</td>
    </tr>
</table>

### Prompt Execution-1

```{python}
# inputs
event = "Assassination of John F Kennedy"
scenario = "What if JFK was not murdered?"
output_type = "news article"
role = "journalist"
additional_instructions = "Be dramatic. You are working for The Sun."

prompt = f"""
    Based on the following Wikipedia summary about the {event}:
    {event_summary}

    f"Take on the role {role} in 2025. Write a {output_type}."
    f"Imagining that the following event in history had a different outcome: {event}."
    f"Consider the following scenario: {scenario} as counterfactual scenario."
    f"{additional_instructions}"
    f"Write it not conditional. Write in active style such that you could think it really happened like this"
"""
```

### Output Execution-1
 THE SUN
-------

*2025 EDITION*






📰 A WORLD REIMAGINED: THE ENDURING LEGACY OF JOHN F. KENNEDY
----------------------------------------------------------



*How One Moment in Dallas Changed the Course of History*



In a twist of fate that continues to ripple through the annals of time, the world reflects
on the profound implications of a reality where John F. Kennedy, the 35th President of the
United States, survived the assassination attempt in Dallas on November 22, 1963. This
alternate timeline presents a fascinating glimpse into a world where leadership and vision
reshaped global dynamics, leading to a legacy that endures to this day.




📰 A Presidency Continued: The Domino Effect of Peace and Progress
---------------------------------------------------------------



Historians in 2025 point to the survival of JFK as a pivotal moment in modern history.
"Kennedy's continued leadership set off a chain reaction of events that altered the
trajectory of the 20th century," remarks Dr. Emily Carter, a leading historian at Harvard
University. Without the tragic interruption of his presidency, Kennedy's commitment to
diplomacy and reform flourished, avoiding the escalation of the Vietnam War and fostering
a more peaceful resolution to the Cold War. His approach to Cuba, marked by cautious
diplomacy, averted the brink of nuclear war, leading to a gradual normalization of
relations.



Domestically, Kennedy's survival accelerated the Civil Rights Movement. His impassioned
advocacy led to the passage of landmark legislation earlier than in our timeline,
fostering racial equality and social justice. This era of progress also saw the Kennedy
brothers—Robert and Ted—playing instrumental roles in shaping American politics, cementing
the Kennedy name as a beacon of leadership and change.




📰 The Butterfly Effect: A World Without Tragedy
---------------------------------------------



The ramifications of JFK's survival extend beyond politics. The cultural landscape of the
1960s and beyond was deeply influenced by his presence. "The optimism and idealism of the
Kennedy era persisted, inspiring generations to strive for public service and social
activism," notes Dr. Michael Grant, a cultural historian. The arts and sciences flourished
under his patronage, and the space program, a pet project of Kennedy's, reached new
frontiers, possibly even achieving a manned Mars landing decades earlier.




📰 A Family Legacy Intact
----------------------



The Kennedy family's political dynasty, unmarred by tragedy, continued to shape American
politics. Robert F. Kennedy, not falling to an assassin's bullet in 1968, went on to win
the presidency, furthering his brother's vision. Ted Kennedy became a Senate stalwart,
championing progressive causes. The Kennedy name remained synonymous with leadership and
integrity, influencing political landscapes well into the 21st century.




📰 Reflections in 2025
-------------------



As we look back, the survival of John F. Kennedy offers a powerful lesson in the fragility
and potential of history. "It's a reminder that individual actions can have monumental
consequences," observes Dr. Carter. The world Kennedy helped build is one of diplomacy,
equality, and hope—a testament to the enduring power of visionary leadership.



In this reimagined world, the legacy of John F. Kennedy is not one of potential cut short,
but of possibilities realized. His story continues to inspire, a beacon of what could have
been, and what, in this alternate reality, became the foundation of a better world.





*This article is part of The Sun's "Rewriting History" series, exploring pivotal moments
that shaped the world we live in today.*