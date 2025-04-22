# Gen AI Intensive Course (Google and Kaggle)

These are my notes and material from the Gen AI Intensive Course offered by Google and Kaggle. The course covers various aspects of Generative AI, including its applications, tools, and ethical considerations.

Credit goes to the amazing people at Google and Kaggle for creating this course and putting together all the material.

## Content

0. [Unit 0: Foundational LLM (Notes)](Unit-0-Foundational-LLM/Notes-and-Summary.md)
1. [Unit 1: Prompt Engineering (Notes)](Unit-1-Prompt-Engineering/Notes-and-Summary.md)
2. [Unit 1: Evaluating LLMs (Notes)](Unit-1-Prompt-Engineering/Notes-Evaluation.md)
3. [Unit 2: Embeddings (Notes)](Unit-2-Embeddings/Notes-and-Summary.md)
4. [Unit 3: Agents (Notes)](Unit-3-Agents/Notes-and-Summary.md)
5. [Capstone Project](Capstone-Project/ai-t-histchronicle.ipynb)

## Capstone Project: AI(t)HistChronicle

This project explores the intersection of AI and counterfactual history — using large language models to generate plausible alternate timelines for pivotal moments in human history.

AI(t)HistChronicle is an AI agent pipeline that combines external knowledge retrieval, structured reasoning (via Tree-of-Thoughts), and controlled text generation to create richly detailed historical narratives based on user-defined “what-if” scenarios.

**AI Capabilities used:**
- RAG (Retrieval Augmented Generation) through feeding in background information from Wikipedia and news articles from Wikinews
- Controlled generation by specifying, for instance, the role the model should take and the output type the response should have
- Structured output (JSON)
- Agents through combination of reasoning, API connection and model output
- Few-shot/ One-shot prompting
- Tree-of-Thoughts (ToT) prompting

**Models used:**
- DeepSeek-R1-Distill-Llama-70B (DeepSeek)
- Llama3–70B–8192 (Meta)

**[Full code](/Cap-Stone/ai-t-histchronicle.ipynb)**

The [notebook](/Cap-Stone/ai-t-histchronicle.ipynb) is part of my submission to the [Gen AI Intensive Course Capstone 2025Q1](https://www.kaggle.com/competitions/gen-ai-intensive-course-capstone-2025q1).

I also wrote a blog post on it. See [@Medium](https://medium.com/@patthie/alternate-realities-powered-by-ai-a-creative-experiment-in-counterfactual-history-30b41ed5b1be)

### Case Study: Berlin Wall

Using the following prompt:

```

# inputs (adjust to the setting you are interested in)
event = "The fall of the Berlin Wall"
scenario = "What if the Berlin Wall never came down?"
output_type = "school textbook page"
role = "lecturer"
additional_instructions = "Be precise. You are writing for 10th graders. Generate also the name of the textbook." # In case you want to give the text a specific twist. If not, leave empty!
text_length = 1000 # number of tokens

prompt = f"""
    Based on the following background on the {event}:
    {background}

    And based on this outline with the title {best_thought["title"]} and the content {best_thought["content"]} 

    Take on the professional role {role} in 2025. Write a detailed {output_type}.
    Imagining that the following event in history had a different outcome: {event}.
    Consider the following scenario: {scenario} as counterfactual scenario.
    {additional_instructions}
    
    Do not write in conditional sentences. Write in active style such that you could think it really happened like this!
"""
```

#### Output

**Textbook Name:** "Alternate Histories: Exploring the What-Ifs of the Past"

📰 Page 234:

📰 A World Divided: The Persistence of the Iron Curtain

As the years went by, the Berlin Wall, erected in 1961, continued to stand tall, a
physical and symbolic barrier between East and West Berlin. The Cold War raged on, with
the United States and the Soviet Union locked in a bitter struggle for global influence.
The division of Germany remained, with the communist East Germany (GDR) firmly under
Soviet control, while West Germany (FRG) aligned itself with the Western Bloc.

The Iron Curtain, a term coined by Winston Churchill in 1946, persisted as a daunting
obstacle to freedom and democracy in Eastern Europe. The Soviet Union maintained its grip
on the region, with communist governments in Poland, Czechoslovakia, Hungary, and other
countries. The Eastern Bloc remained a closely guarded and isolated entity, cut off from
the rest of Europe and the world.

The consequences of this prolonged division were far-reaching. The flow of people, ideas,
and goods between East and West remained severely restricted. The economies of Eastern
European countries stagnated, while the West continued to prosper. The cultural and
educational exchange programs that had begun to flourish in the late 1980s came to a halt,
as the borders remained closed.

In the absence of the fall of the Berlin Wall, the wave of democratic revolutions that
swept across Eastern Europe in 1989 never materialized. The Velvet Revolution in
Czechoslovakia, the Polish Round Table Talks, and the Hungarian reforms were all
stillborn. The Soviet Union, under the leadership of Mikhail Gorbachev, continued to exert
its control over the region, suppressing any dissent and opposition.

The global implications of this scenario were profound. The Cold War continued to dominate
international relations, with the United States and the Soviet Union engaging in a series
of proxy wars, espionage, and ideological battles around the world. The United Nations
remained a weakened institution, unable to effectively address global crises.

In this world, Germany remained divided, with the wall serving as a constant reminder of
the deep ideological and political divisions that separated the two nations. The European
Union, founded in 1993, was still a distant dream, as the continent remained fragmented
and at odds.

As the years went by, the world became increasingly polarized, with the East-West divide
hardening into an impenetrable barrier. The possibilities of peaceful coexistence,
détente, and globalization seemed like a distant memory, as the world was trapped in a
state of perpetual tension and division.

📰 Questions for Discussion:

1. How did the persistence of the Berlin Wall affect the economies of Eastern Europe?

2. What were the implications of the continued division of Germany for European politics?

3. How did the absence of democratic revolutions in Eastern Europe impact global politics?

4. What would have been the long-term consequences of a continued Cold War?

📰 Activities:

1. Create a timeline of major events in Eastern Europe and Germany from 1989 to 2000,
assuming the Berlin Wall never fell.

2. Imagine you are a citizen of East Germany in 1995. Write a diary entry describing your
daily life under communist rule.

3. Research and write a short essay on the impact of the continued Cold War on
international relations and global security.

![Textbook page for Berlin Wall case study](/Cap-Stone/Alternate_Histories_Textbook_Page.png)
<h6 style="text-align: center"><strong>Textbook page for Berlin Wall case study</strong></h6>

### Case Study: JFK

Using the following prompt:

```{python}	
# inputs (adjust to the setting you are interested in)
event = "Assassination of John F Kennedy"
scenario = "What if JFK was not murdered?"
output_type = "news article"
role = "journalist"
additional_instructions = "Be dramatic. You are working Tabloid journalism newspaper. Also create a name for this newspaper" # In case you want to give the text a specific twist. If not, leave empty!
text_length = 1000 # number of tokens

prompt = f"""
    Based on the following background on the {event}:
    {background}

    And based on this outline with the title {best_thought["title"]} and the content {best_thought["content"]} 

    Take on the professional role {role} in 2025. Write a detailed {output_type}.
    Imagining that the following event in history had a different outcome: {event}.
    Consider the following scenario: {scenario} as counterfactual scenario.
    {additional_instructions}
    
    Do not write in conditional sentences. Write in active style such that you could think it really happened like this!
"""
```

#### Output

📰 THE DAILY SCOOP

📰 VOL. 1, NO. 23, MARCH 20, 2025

📰 KENNEDY'S LEGACY: A PRESIDENCY UNINTERRUPTED

In a world where fate took a dramatic turn, John F. Kennedy, the 35th President of the
United States, survived the assassination attempt on November 22, 1963, in Dallas, Texas.
Today, we celebrate the remarkable legacy of a leader who changed the course of history.

📰 Vietnam War: A Different Chapter

With Kennedy at the helm, the United States took a more cautious approach to the Vietnam
War. He resisted pressure from hawkish advisors, opting for diplomatic efforts to resolve
the conflict. His leadership led to increased international pressure on North Vietnam,
resulting in a negotiated peace treaty in 1966, two years earlier than the actual signing
of the Paris Peace Accords.

The early resolution of the war prevented the loss of thousands of American lives and
avoided the devastating impact of the war on the US economy. The saved resources were
instead invested in domestic programs, such as education and infrastructure development,
cementing Kennedy's reputation as a forward-thinking leader.

📰 Civil Rights Advancements

Kennedy's unwavering commitment to civil rights propelled the movement forward at an
unprecedented pace. His leadership ensured the swift passage of the Civil Rights Act of
1964, outlawing discrimination based on race, color, religion, sex, or national origin.
This landmark legislation paved the way for the Voting Rights Act of 1965, further
solidifying Kennedy's legacy as a champion of equality.

Under Kennedy's guidance, the nation witnessed a series of significant milestones,
including the desegregation of public facilities, the integration of schools, and the
appointment of African Americans to key government positions. His leadership fostered a
climate of inclusivity, paving the way for future generations of civil rights leaders.

📰 Space Exploration: The Next Frontier

Kennedy's vision for space exploration continued to propel the United States forward, with
NASA's Apollo program achieving remarkable breakthroughs. In 1967, the first human
settlement on the moon was established, marking a historic milestone in space exploration.
The scientific discoveries and technological advancements that followed have transformed
our understanding of the universe and inspired new generations of innovators.

📰 A Different 1960s and Beyond

Kennedy's leadership had a profound impact on the cultural and social landscape of the
1960s. His presidency inspired a new wave of optimism, activism, and creativity, shaping
the decade's defining moments. The music, art, and literature of the era were influenced
by his message of hope and progress.

Today, as we reflect on the what-ifs of history, we are reminded that the course of human
events is fragile and subject to the whims of fate. Yet, in this alternate reality,
Kennedy's unwavering commitment to his vision has left an indelible mark on our world.

In the words of the man himself, "Let every nation know, whether it wishes us well or ill,
that we shall pay any price, bear any burden, meet any hardship, support any friend,
oppose any foe to assure the survival and the success of liberty."

**THE DAILY SCOOP** invites readers to share their thoughts on this fascinating
counterfactual scenario. Join the conversation on our social media channels and let us
know: What do you think would have been different if JFK had lived?

![JFK Daily Scoop](/Cap-Stone/Canva_Frontpage_JFK_Daily_Scoop.png)
<h6 style="text-align: center"><strong>JFK Daily Scoop</strong></h6>