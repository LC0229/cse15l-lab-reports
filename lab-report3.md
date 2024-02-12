# LabReport3

 *Name: ShengruiChen*
 
 *Email:shc067@ucsd.edu*

## Part1-Bugs


* failure-inducing input

```java

import static org.junit.Assert.*;
import org.junit.*;

@Test
  public void testReversed2() {
    int[] input2 = { 1,2,3};
    assertArrayEquals(new int[]{ 3,2,1}, ArrayExamples.reversed(input2));
```


* input that doesn't induce a failure
 ```java
@Test
  public void testReversed1() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

* Symptom
  
![Screenshot 2024-02-10 at 8 38 17 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/2d044ba8-488d-41b3-84b1-63fe5624d837)

![Screenshot 2024-02-10 at 8 38 27 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/96c73408-088e-47de-a538-dbd9a8968a9d)

  
* Before
```java

static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

* After
```java

  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```



Explanation:
We can see that after we created an int array called newArray, it contains 0s with the same length as arr. The problem happens at assigning part, we are assigning 0 to all index of arr, which should be reversed. Since based on screenshots, we always see the 0 for actual. By assignning the arr elements reversely into newArray, we can simply return newArray as the result of reversed method.




## Part1-Less Commands

*Case1 less -E

less automatically exits upon reaching the end of file.

(https://phoenixnap.com/kb/less-command-in-linux)

Example1:

```java
chenshengrui@zuis-MacBook-Pro technical % less -E plos/journal.pbio.0020001.txt

 Kofi Annan, the Secretary-General of the United Nations, recently called attention to
        the clear inequalities in science between developing and developed countries and to the
        challenges of building bridges across these gaps that should bring the United Nations and
        the world scientific community closer to each other (Annan 2003). Mr. Annan stressed the
        importance of reducing the inequalities in science between developed and developing
        countries, asserting that “This unbalanced distribution of scientific activity generates
        serious problems not only for the scientific community in the developing countries, but for
        development itself.” Indeed, Mr. Annan's sentiments have also been echoed recently by
        several scientists, who present overwhelming evidence for the disparity in scientific
        output between the developing and already developed countries (Gibbs 1995; May 1997;
        Goldemberg 1998; Riddoch 2000). For example, recent United Nations Educational, Scientific,
        and Cultural Organization (UNESCO) estimates (UNESCO 2001) indicate that, in 1997, the
        developed countries accounted for some 84% of the global investment in scientific research
        and development, had approximately 72% of the world researchers, and produced approximately
        88% of all scientific and technical publications registered by the Science Citation Index
        (SCI). North America and Europe clearly dominate the number of scientific publications
        produced annually, with 36.6% and 37.5%, respectively, worldwide (UNESCO 2001).
        
          
            North America and Europe clearly dominate the number of scientific
            publications produced annually.
          
        
        It is rather obvious that richer countries are able to invest more resources in science
        and therefore account for the largest number of publications. It is also likely that there
        is a statistical bias on the part of the SCI as a bibliometric database, since it
        represents North American and European publications far better than those of the rest of
        the world (Gibbs 1995; May 1997; Alonso and Fernández-Juricic 2001; Vohora and Vohora
        2001). But is the disparity in scientific contributions between the developed and
        developing worlds actually remaining unchanged or even increasing, as Mr. Annan has
        implied? A closer look at the trends over the last decade reveals important advances in
        developing countries. For example, Latin America and China, although representing,
        respectively, only 1.8% and 2% of scientific publications worldwide, have increased the
        number of their publications between 1990 and 1997 by 36% and 70%, respectively, which is a
        much higher percentage than the increments reached by Europe (10%) and industrial Asia
        (26%). The percentage of global scientific publications from North America actually
        decreased by 8% over the same period (UNESCO 2001).
      
      
        Publishing Trends in the Americas
        Using the SCI databases produced by the Institute for Scientific Information (ISI), as
        well as data compiled by the Red Iberoamericana de Indicadores de Ciencia y Tecnología
        (RICYT), we examined the differences in the number and proportion of scientific
        publications between the developed world and the developing world from 1990 until 2000,
        focusing on the Americas as a case study. Not surprisingly, there was a huge disparity in
        the number of publications from 1990 until 2000, with the United States contributing the
        lion's share (84.2%), followed by Canada (10.35%). Latin America as a whole contributed
        only 5.45% to the total number of scientific publications in these ten years (RICYT
        2002).
        The total number of publications, however, is not necessarily the best measure for
        assessing scientific productivity or technical advances (May 1997). More relevant
        measurements for these factors include the proportional change in the number of
        publications and the total number of publications when corrected for investment in research
        and development (May 1997). The proportional change in the number of publications, using
        1990 as a comparison, revealed that scientific publishing in Latin America increased the
        most rapidly in the Americas, far outpacing the United States and Canada (Figure 1).
        Further analyses, correcting the number of overall publications for the amount of money
        invested in research and development for each region, also show that, in contrast to both
        Canada and United States, the trend in Latin America has been an increase in relative
        output throughout the 1990s (Figure 2). Moreover, when taking into account the amount of
        research money available to researchers, Latin America actually out-published the United
        States and Canada by the year 2000 (Figure 2). Although the cost of research is undoubtedly
        cheaper in the developing world due to relatively low researcher salaries, overhead and
        other work standards, these factors do not explain the substantial increase in the number
        of publications per amount of money allocated to research and development in Latin America,
        particularly from 1995 until 2000 (Figure 2).
        Other relative indicators of scientific productivity, such as the number of publications
        picked up by the SCI in relation to the number of scientists in a particular country, also
        demonstrate that such developing regions as Latin America are making substantial
        contributions to science, despite the fact that the average proportion of gross domestic
        product (GDP) invested in science in Latin America throughout this 10-year period was only
        21% of the amount invested in United States (RICYT 2002). Indeed, this scientific
        productivity is remarkable when we compare it with the relatively low investment in science
        itself as compared with the GDP of Latin America as a whole. In fact, Albornoz (2001)
        concluded that, as a group, Latin America could afford to invest a much higher proportion
        of its resources in scientific research and development. Latin American investment in
        research and development represented only 0.59% of the regional GDP in 1998, a very weak
        effort compared with that of the United States (2.84%) and Canada (1.5%).
        Among Latin American countries, there is a high degree of variability in publication
        rate as well as in financial investment in science and technology. Some countries have
        performed particularly well. For example, Uruguay, Chile, Panama, and Cuba averaged,
        respectively, 6.8, 5.3, 5.2, and 3.4 publications per million dollars of research and
        development investment in the 10 years studied, which is notoriously high compared with
        United States (1.5) and even Canada (3.3) (RICYT 2002). Other countries, such as Costa
        Rica, Cuba, Brazil, and Chile, have invested a much greater proportion of their GDP in
        research and development than the other countries of this region (Albornoz 2001).
        
          
            Why has the number of publications per dollar invested in research and
            development been increasing in Latin America while decreasing in United States and
            Canada?
          
        
      
      
        Explaining the Increase in Publishing Productivity in Latin America
        One potential explanation for the increase in scientific productivity in Latin America
        is that scientific development during the 1990s was particularly strong for many countries
        of this region. Indeed, this would explain the rapid rise in the number of publications in
        Latin America compared with the relatively flat increases in the United States and Canada,
        which were publishing just as well at the beginning of the decade. A potentially more
        important question, however, is why the number of publications per dollar invested in
        research and development has been increasing in Latin America while decreasing in the
        United States and Canada. This pattern could be the result of a variety of factors, none of
        which are mutually exclusive. It is possible that publishing in international journals as a
        measure of scientific productivity is becoming more important in Latin America. Increased
        funding to the most productive scientists from the national science development programs
        might have been an important stimulus. International cooperation resulting in more
        scientific collaborations among scientists in Latin America, Europe, and the United States
        may also have increased the relative number of publications in Latin America. In contrast,
        the decreasing trends in the number of publications per investment dollar in Canada and
        United States could reflect a trend towards more costly research in larger scientific
        programs.
      
      
        Scientific Impact from Latin America
        What, exactly, is the relative impact of such developing regions as Latin America on the
        scientific community? We used SCI 2001 data to examine the proportion of publications in
        the area of ecology (including the fields of evolutionary biology, conservation biology,
        and global change biology) between 1990 and 2002 in both the two top general science
        journals (
        Nature and 
        Science ; with impact factors of 27.96 and 23.33, respectively) and in
        the 20 top ecological journals (with impact factors of 10.51–2.47) (ISI 2001a). We credited
        a region with a publication if any of the authors were affiliated with institutions from
        that region. Thus, more than one region would receive credit for a single publication if
        that publication had been written by multiple authors from institutions of different
        regions.
        For the top 20 ecological journals, the American subcontinents of South, Central, and
        North America accounted for 62% of the publications worldwide. Within the Americas,
        however, Latin America represented only 6%, while Canada and United States accounted,
        respectively, for 13% and 82% of the top 20 ecological publications. When we examined the
        data as contributions to the top 10 ecological journals (impact factors 10.51–3.31) versus
        the top 11–20 (impact factors 3.28–2.47), the Latin American countries contributed nearly
        twice as many publications to journals in the second category (8% in the top 11–20 compared
        with 4% in the top 10). These findings suggest that publications from such developing
        regions as Latin America are falling short of reaching the top journals. In contrast, the
        United States contributed somewhat more publications to the top 10 journals (84%) than the
        top 11–20 journals (79%). The difference in the proportion of publications contributed by
        the United States to the top 10 and top 20 journals was even more pronounced when we
        examined it in respect to worldwide publications. In this case, the United States
        contributed 60% of the publications to the top 10 journals and only 40% of the publications
        to the top 11–20 journals.
        Interestingly, the proportion of publications from Latin America, the United States, and
        Canada across all subject areas in 
        Science and 
        Nature were nearly identical to those of the top 20 ecological journals.
        In 
        Science and 
        Nature , Latin America had 7% of the publications within the Americas
        versus 6% in the top 20 ecological journals, whereas the United States and Canada had 81%
        versus 82% and 12% versus 13%, respectively. These similarities suggest that the Latin
        American researchers are not shying away from the two top-ranked general science journals.
        However, publishing in 
        Science and 
        Nature was not enough to gain prominence, as evidenced by the number of
        citations of these researchers. The latest list of the 247 most-cited researchers in
        ecology and environmental sciences emphasizes the overwhelming contributions of authors
        from North America (73%) and Europe (21%) (ISI 2001b). No researcher working in a Latin
        American institution was included in the remaining 6%. Overall, these data indicate that
        the scientific output in the field of ecology in Latin America is having a relatively low
        impact in the international scientific community and is underrepresented in the top
        international journals, despite its robust productivity as measured by the number of
        publications per researcher funding amount. Similar findings were also reported for Asia
        (Swinbanks et al. 1997) and thus could be a general phenomenon in the developing world.
        Although there are outstanding scientific researchers in the developing world who
        independently are making important contributions to the international scientific community,
        they are the exception. Why, in general, do Latin American scientists often fail to reach
        the top journals or become amongst the most cited researchers in their fields? One
        possibility is that the main research agendas between both regions are somewhat different
        and that the top journals, which are published in the developed world, respond more to the
        scientific mainstream of the developed regions. This is not to suggest any sort of
        conspiracy, but rather it implies that the perception of the most important science is
        linked to the region and that because the major funding agencies as well as most prominent
        journals share a similar economic region, they also share the same perception of what
        science is most interesting to them. Another consideration is that more local journals from
        developed regions are listed by the SCI than similar journals from developing regions
        (Gibbs 1995). Consequently, there are more high-profile regional publication opportunities
        available to scientists from the developed region, whereas much of the research published
        locally in the developing world is overlooked. But it takes more than publishing good
        papers to become a highly cited scientist. It requires attending international meetings and
        introducing novel research findings in multiple scientific forums. Funding these
        activities, however, requires a greater proportion of research money being spent on
        meetings for researchers in the developing compared with the developed world.
      
      
        A Long Road Yet to Travel
        The positive trends in scientific productivity in Latin America should not be
        misinterpreted as a reason to be unconcerned about the existing gap highlighted by Mr.
        Annan. There are many compelling reasons for the push to increase scientific input from the
        developing world (Goldemberg 1998; Annan 2003). One is that science, as a discipline, would
        benefit from the contributions of many disparate groups around the world, rather than being
        dominated by two geographic regions. Many scientific problems could be solved much more
        readily with the cooperation and scientific insight of scientists from developing regions.
        Climate change and biodiversity research, for example, urgently need the scientific input
        from those developing regions that are so important for these global processes. It is also
        critical for the developing world to promote, through research and publications, those
        areas of concern that are having a proportionally greater scientific and social impact upon
        them. There are now examples in which research on priority areas for the developing nations
        can actually become pioneering work in areas neglected by the research agenda of the
        industrialized world. This has been the case for research on renewable energy sources in
        Brazil (Goldemberg 1998) and biomedical sciences in Cuba (Castro Díaz-Balart 2002). These
        examples are important not only for those regions of the developing world, but are also in
        themselves scientific innovations that can greatly advance the knowledge of the rest of the
        world.
        
          
            Climate change and biodiversity research urgently need the scientific
            input from those developing regions that are so important for global processes.
          
        
        Although the evidence presented here demonstrates that there is a long way to go before
        developing countries contribute a more equitable share to the international scientific
        community, there are also reasons to be optimistic. The relative increase in the number of
        publications, especially when corrected for the amount of money available in research and
        development, demonstrates that many developing countries are heading in the right
        direction. The extremely high scientific productivity of many developing nations, corrected
        for and despite the rather limited availability of funds, suggests that increased funding
        to the sciences will be an excellent investment by developing nations in terms of
        publications as a measure of scientific output, particularly if these publications can
        target the journals that have the greatest impact. Although there may still be a long road
        to travel, we feel optimistic that the bridges mentioned by Mr. Annan are slowly being
        built.
      
 chenshengrui@zuis-MacBook-Pro technical %    

```

Compared to less, less - E automatically exits upon reaching the end of journal.pbio.0020001.txt, which is useful if we want to do a quick check for the content of the file.


Example2:

```java

chenshengrui@zuis-MacBook-Pro technical % less -E 911report/preface.txt
 PREFACE
            We present the narrative of this report and the recommendations that flow from it to
                the President of the United States, the United States Congress, and the American
                people for their consideration. Ten Commissioners-five Republicans and five
                Democrats chosen by elected leaders from our nation's capital at a time of great
                partisan division-have come together to present this report without dissent.
            We have come together with a unity of purpose because our nation demands it.
                September 11, 2001, was a day of unprecedented shock and suffering in the history of
                the United States. The nation was unprepared. How did this happen, and how can we
                avoid such tragedy again?
            To answer these questions, the Congress and the President created the National
                Commission on Terrorist Attacks Upon the United States (Public Law 107-306, November
                27, 2002).
            Our mandate was sweeping. The law directed us to investigate "facts and circumstances
                relating to the terrorist attacks of September 11, 2001," including those relating
                to intelligence agencies, law enforcement agencies, diplomacy, immigration issues
                and border control, the flow of assets to terrorist organizations, commercial
                aviation, the role of congressional oversight and resource allocation, and other
                areas determined relevant by the Commission. In pursuing our mandate, we have
                reviewed more than 2.5 million pages of documents and interviewed more than 1,200
                individuals in ten countries. This included nearly every senior official from the
                current and previous administrations who had responsibility for topics covered in
                our mandate. We have sought to be independent, impartial, thorough, and nonpartisan.
                From the outset, we have been committed to share as much of our investigation as we
                can with the American people. To that end, we held 19 days of hearings and took
                public testimony from 160 witnesses.
            Our aim has not been to assign individual blame. Our aim has been to provide the
                fullest possible account of the events surrounding 9/11 and to identify lessons
                learned.
            We learned about an enemy who is sophisticated, patient, disciplined, and lethal. The
                enemy rallies broad support in the Arab and Muslim world by demanding redress of
                political grievances, but its hostility toward us and our values is limitless. Its
                purpose is to rid the world of religious and political pluralism, the plebiscite,
                and equal rights for women. It makes no distinction between military and civilian
                targets. Collateral damage is not in its lexicon.
            We learned that the institutions charged with protecting our borders, civil aviation,
                and national security did not understand how grave this threat could be, and did not
                adjust their policies, plans, and practices to deter or defeat it. We learned of
                fault lines within our government-between foreign and domestic intelligence, and
                between and within agencies. We learned of the pervasive problems of managing and
                sharing information across a large and unwieldy government that had been built in a
                different era to confront different dangers.
            At the outset of our work, we said we were looking backward in order to look forward.
                We hope that the terrible losses chronicled in this report can create something
                positive-an America that is safer, stronger, and wiser. That September day, we came
                together as a nation. The test before us is to sustain that unity of purpose and
                meet the challenges now confronting us. We need to design a balanced strategy for
                the long haul, to attack terrorists and prevent their ranks from swelling while at
                the same time protecting our country against future attacks. We have been forced to
                think about the way our government is organized. The massive departments and
                agencies that prevailed in the great struggles of the twentieth century must work
                together in new ways, so that all the instruments of national power can be combined.
                Congress needs dramatic change as well to strengthen oversight and focus
                accountability.
            As we complete our final report, we want to begin by thanking our fellow
                Commissioners, whose dedication to this task has been profound. We have reasoned
                together over every page, and the report has benefited from this remarkable
                dialogue. We want to express our considerable respect for the intellect and judgment
                of our colleagues, as well as our great affection for them.
            We want to thank the Commission staff. The dedicated professional staff, headed by
                Philip Zelikow, has contributed innumerable hours to the completion of this report,
                setting aside other important endeavors to take on this all-consuming assignment.
                They have conducted the exacting investigative work upon which the Commission has
                built. They have given good advice, and faithfully carried out our guidance. They
                have been superb. We thank the Congress and the President. Executive branch agencies
                have searched records and produced a multitude of documents for us. We thank
                officials, past and present, who were generous with their time and provided us with
                insight. The PENTTBOM team at the FBI, the Director's Review Group at the CIA, and
                Inspectors General at the Department of Justice and the CIA provided great
                assistance. We owe a huge debt to their investigative labors, painstaking attention
                to detail, and readiness to share what they have learned. We have built on the work
                of several previous Commissions, and we thank the Congressional Joint Inquiry, whose
                fine work helped us get started. We thank the City of New York for assistance with
                documents and witnesses, and the Government Printing Office and W.W. Norton
                & Company for helping to get this report to the broad public.
            We conclude this list of thanks by coming full circle: We thank the families of 9/11,
                whose persistence and dedication helped create the Commission. They have been with
                us each step of the way, as partners and witnesses. They know better than any of us
                the importance of the work we have undertaken.
            We want to note what we have done, and not done. We have endeavored to provide the
                most complete account we can of the events of September 11, what happened and why.
                This final report is only a summary of what we have done, citing only a fraction of
                the sources we have consulted. But in an event of this scale, touching so many
                issues and organizations, we are conscious of our limits. We have not interviewed
                every knowledgeable person or found every relevant piece of paper. New information
                inevitably will come to light. We present this report as a foundation for a better
                understanding of a landmark in the history of our nation.
            We have listened to scores of overwhelming personal tragedies and astounding acts of
                heroism and bravery. We have examined the staggering impact of the events of 9/11 on
                the American people and their amazing resilience and courage as they fought back. We
                have admired their determination to do their best to prevent another tragedy while
                preparing to respond if it becomes necessary. We emerge from this investigation with
                enormous sympathy for the victims and their loved ones, and with enhanced respect
                for the American people. We recognize the formidable challenges that lie ahead.
            We also approach the task of recommendations with humility. We have made a limited
                number of them. We decided consciously to focus on recommendations we believe to be
                most important, whose implementation can make the greatest difference. We came into
                this process with strong opinions about what would work. All of us have had to
                pause, reflect, and sometimes change our minds as we studied these problems and
                considered the views of others. We hope our report will encourage our fellow
                citizens to study, reflect-and act.
            Thomas H. Kean, chair
            Lee H. Hamilton, vice chair

chenshengrui@zuis-MacBook-Pro technical %
```

When we read a book like 911report, we want to do a quick check for the preface of the book. At here, we used less -E command, which helps us to do a quick review and I don't want use `less` to open it and wait for my command to exit.


*Case2 less -N

Displays line numbers at the beginning of each line.

(https://phoenixnap.com/kb/less-command-in-linux)

Example1:

```java
chenshengrui@zuis-MacBook-Pro technical % less -N 911report/preface.txt
      1 
      2     
      3         
      4             PREFACE
      5             We present the narrative of this report and the recommendations that flow from it to
      6                 the President of the United States, the United States Congress, and the American
      7                 people for their consideration. Ten Commissioners-five Republicans and five
      8                 Democrats chosen by elected leaders from our nation's capital at a time of great
      9                 partisan division-have come together to present this report without dissent.
     10             We have come together with a unity of purpose because our nation demands it.
     11                 September 11, 2001, was a day of unprecedented shock and suffering in the history of
     12                 the United States. The nation was unprepared. How did this happen, and how can we
     13                 avoid such tragedy again?
     14             To answer these questions, the Congress and the President created the National
     15                 Commission on Terrorist Attacks Upon the United States (Public Law 107-306, November
     16                 27, 2002).
     17             Our mandate was sweeping. The law directed us to investigate "facts and circumstances
     18                 relating to the terrorist attacks of September 11, 2001," including those relating
     19                 to intelligence agencies, law enforcement agencies, diplomacy, immigration issues
     20                 and border control, the flow of assets to terrorist organizations, commercial
     21                 aviation, the role of congressional oversight and resource allocation, and other
     22                 areas determined relevant by the Commission. In pursuing our mandate, we have
     23                 reviewed more than 2.5 million pages of documents and interviewed more than 1,200
     24                 individuals in ten countries. This included nearly every senior official from the
     25                 current and previous administrations who had responsibility for topics covered in
     26                 our mandate. We have sought to be independent, impartial, thorough, and nonpartisan.
     27                 From the outset, we have been committed to share as much of our investigation as we
     28                 can with the American people. To that end, we held 19 days of hearings and took
     29                 public testimony from 160 witnesses.
     30             Our aim has not been to assign individual blame. Our aim has been to provide the
     31                 fullest possible account of the events surrounding 9/11 and to identify lessons
     32                 learned.
     33             We learned about an enemy who is sophisticated, patient, disciplined, and lethal. The
     34                 enemy rallies broad support in the Arab and Muslim world by demanding redress of
     35                 political grievances, but its hostility toward us and our values is limitless. Its
     36                 purpose is to rid the world of religious and political pluralism, the plebiscite,
     37                 and equal rights for women. It makes no distinction between military and civilian
     38                 targets. Collateral damage is not in its lexicon.
     39             We learned that the institutions charged with protecting our borders, civil aviation,
     40                 and national security did not understand how grave this threat could be, and did not
     41                 adjust their policies, plans, and practices to deter or defeat it. We learned of
     42                 fault lines within our government-between foreign and domestic intelligence, and
     43                 between and within agencies. We learned of the pervasive problems of managing and
     44                 sharing information across a large and unwieldy government that had been built in a
     45                 different era to confront different dangers.
     46             At the outset of our work, we said we were looking backward in order to look forward.
     47                 We hope that the terrible losses chronicled in this report can create something
     48                 positive-an America that is safer, stronger, and wiser. That September day, we came
     49                 together as a nation. The test before us is to sustain that unity of purpose and
     50                 meet the challenges now confronting us. We need to design a balanced strategy for
     51                 the long haul, to attack terrorists and prevent their ranks from swelling while at
     52                 the same time protecting our country against future attacks. We have been forced to
     53                 think about the way our government is organized. The massive departments and
     54                 agencies that prevailed in the great struggles of the twentieth century must work
     55                 together in new ways, so that all the instruments of national power can be combined.
     56                 Congress needs dramatic change as well to strengthen oversight and focus
     57                 accountability.
     58             As we complete our final report, we want to begin by thanking our fellow
     59                 Commissioners, whose dedication to this task has been profound. We have reasoned
     60                 together over every page, and the report has benefited from this remarkable
     61                 dialogue. We want to express our considerable respect for the intellect and judgment
     62                 of our colleagues, as well as our great affection for them.
     63             We want to thank the Commission staff. The dedicated professional staff, headed by
     64                 Philip Zelikow, has contributed innumerable hours to the completion of this report,
     65                 setting aside other important endeavors to take on this all-consuming assignment.
     66                 They have conducted the exacting investigative work upon which the Commission has
     67                 built. They have given good advice, and faithfully carried out our guidance. They
     68                 have been superb. We thank the Congress and the President. Executive branch agencies
     69                 have searched records and produced a multitude of documents for us. We thank
     70                 officials, past and present, who were generous with their time and provided us with
     71                 insight. The PENTTBOM team at the FBI, the Director's Review Group at the CIA, and
     72                 Inspectors General at the Department of Justice and the CIA provided great
     73                 assistance. We owe a huge debt to their investigative labors, painstaking attention
     74                 to detail, and readiness to share what they have learned. We have built on the work
     75                 of several previous Commissions, and we thank the Congressional Joint Inquiry, whose
     76                 fine work helped us get started. We thank the City of New York for assistance with
     77                 documents and witnesses, and the Government Printing Office and W.W. Norton
     78                 & Company for helping to get this report to the broad public.
     79             We conclude this list of thanks by coming full circle: We thank the families of 9/11,
     80                 whose persistence and dedication helped create the Commission. They have been with
     81                 us each step of the way, as partners and witnesses. They know better than any of us
     82                 the importance of the work we have undertaken.
     83             We want to note what we have done, and not done. We have endeavored to provide the
     84                 most complete account we can of the events of September 11, what happened and why.
     85                 This final report is only a summary of what we have done, citing only a fraction of
     86                 the sources we have consulted. But in an event of this scale, touching so many
     87                 issues and organizations, we are conscious of our limits. We have not interviewed
     88                 every knowledgeable person or found every relevant piece of paper. New information
     89                 inevitably will come to light. We present this report as a foundation for a better
     90                 understanding of a landmark in the history of our nation.
     91             We have listened to scores of overwhelming personal tragedies and astounding acts of
     92                 heroism and bravery. We have examined the staggering impact of the events of 9/11 on
     93                 the American people and their amazing resilience and courage as they fought back. We
     94                 have admired their determination to do their best to prevent another tragedy while
     95                 preparing to respond if it becomes necessary. We emerge from this investigation with
     96                 enormous sympathy for the victims and their loved ones, and with enhanced respect
     97                 for the American people. We recognize the formidable challenges that lie ahead.
     98             We also approach the task of recommendations with humility. We have made a limited
     99                 number of them. We decided consciously to focus on recommendations we believe to be
    100                 most important, whose implementation can make the greatest difference. We came into
    101                 this process with strong opinions about what would work. All of us have had to
    102                 pause, reflect, and sometimes change our minds as we studied these problems and
    103                 considered the views of others. We hope our report will encourage our fellow
    104                 citizens to study, reflect-and act.
    105             Thomas H. Kean, chair
    106             Lee H. Hamilton, vice chair
    107         
    108     
(END)
```

The less -N command gives the lines of number for each line in preface.txt, which helps us to track information in a .txt file at specific line.


Example2:

```java
chenshengrui@zuis-MacBook-Pro technical % less -N  plos/pmed.0010047.txt 
      1 
      2   
      3     
      4       
      5         
      6         A malaria vaccine called ME-TRAP, which targets the pre-erythrocytic stage of the
      7         disease, was not effective at reducing natural infection rates in semi-immune African
      8         adults, according to the report of a randomized controlled trial published this month in 
      9         PLoS Medicine . “This first field efficacy trial was an important
     10         milestone in the progression of new recombinant vectored vaccines to deployable products,”
     11         says Adrian Hill (University of Oxford, United Kingdom), the lead investigator of the
     12         study. “The safety profile was excellent and the efficacy data provide a first indication
     13         of the levels of cellular immunogenicity that will be required for preventing infection,”
     14         he says.
     15         Hill and his co-workers used a heterologous prime–boost vaccination technique. They gave
     16         the volunteers two vaccines—a DNA priming vaccine followed by a modified vaccinia virus
     17         Ankara (MVA) that acted as a booster. The DNA and MVA vaccines both had the same insert
     18         coding for thrombospondin-related adhesion protein (TRAP; a pre-erythrocytic antigen) and a
     19         string of T cell epitopes (called ME for “multiple epitopes”).
     20         Hill's team had previously shown that ME-TRAP vaccines given in prime–boost sequence
     21         could induce large T cell responses in healthy volunteers from the UK and could delay
     22         parasitemia in a sporozoite challenge test (Nat Med 9: 729–735). The next step was to do a
     23         randomized controlled trial in Gambia to determine whether this vaccination strategy could
     24         provide protection against natural 
     25         Plasmodium falciparum infection.
     26         The researchers recruited volunteers from 13 Gambian villages that were close to the
     27         alluvial flood plain and so were at high risk of developing malaria. They randomly assigned
     28         the 372 volunteers to receive either two doses of the DNA ME-TRAP vaccine followed by a
     29         single dose of MVA ME-TRAP, or three doses of rabies vaccine. This three-dose schedule is
     30         similar to the one used by the World Health Organization/United Nations Children's Fund
     31         Expanded Program on Immunization. Two weeks before the third dose was given, all the
     32         volunteers received antimalarial drugs to clear blood-stage 
     33         P. falciparum infections.
     34         The time to first infection, the primary end point of the study, was similar in the two
     35         groups, with an estimated vaccine efficacy of only 10%. However, the effector T cell
     36         response to the TRAP antigen T9/96, measured one week after the third vaccination, was 80
     37         times higher in the DNA/MVA vaccine group than in the rabies vaccine group.
     38         “It is absolutely crucial that results like these are published, since the failures, as
     39         well as the successes, need to be documented if we are to move towards rational strategies
     40         for optimizing malaria vaccines,” says Tom Smith from the Swiss Tropical Institute, who was
     41         not involved in the study. “At the same time, it makes sense to move on quickly without
     42         shedding too many tears, in a field that is moving much faster than it was before the
     43         recent injections of money from the Gates Foundation, but where it is still impossible to
     44         second-guess the results of field trials. This is partly because we do not have any good
     45         proxy measures of effective immunity in 
     46         P. falciparum , and partly because this is a fertile area for
     47         trying out new techniques, such as DNA vaccines, where there is still a lot to learn.”
     48         Hill is planning to do further trials that address the important question of whether
     49         this type of vaccine can prevent the symptoms of malaria. “The next step,” says Hill, “is
     50         to assess newer vaccine regimes that employ two viral vectors rather than DNA and to study
     51         prevention of malaria rather than infection.”
     52       
     53     
     54   
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
(END)
chenshengrui@zuis-MacBook-Pro technical %
```
The less -N command gives the lines of number for each line for the context we input. When it comes to a large file, the use of number lines is really important. When we are processing text files, having line numbers available can be helpful for extracting specific lines or performing operations based on line numbers.


*Case3 less -s
It's merging consecutive blank lines into a single blank line, saving spaces and time for scrolling.

(https://phoenixnap.com/kb/less-command-in-linux)

I put screenshots since I did not see if github page shows single space for content

Example1:

```java
chenshengrui@zuis-MacBook-Pro technical % less -s 911report/preface.txt  

            PREFACE
            We present the narrative of this report and the recommendations that flow from it to
                the President of the United States, the United States Congress, and the American
                people for their consideration. Ten Commissioners-five Republicans and five
                Democrats chosen by elected leaders from our nation's capital at a time of great
                partisan division-have come together to present this report without dissent.
            We have come together with a unity of purpose because our nation demands it.
                September 11, 2001, was a day of unprecedented shock and suffering in the history of
                the United States. The nation was unprepared. How did this happen, and how can we
                avoid such tragedy again?
            To answer these questions, the Congress and the President created the National
                Commission on Terrorist Attacks Upon the United States (Public Law 107-306, November
                27, 2002).
            Our mandate was sweeping. The law directed us to investigate "facts and circumstances
                relating to the terrorist attacks of September 11, 2001," including those relating
                to intelligence agencies, law enforcement agencies, diplomacy, immigration issues
                and border control, the flow of assets to terrorist organizations, commercial
                aviation, the role of congressional oversight and resource allocation, and other
                areas determined relevant by the Commission. In pursuing our mandate, we have
                reviewed more than 2.5 million pages of documents and interviewed more than 1,200
                individuals in ten countries. This included nearly every senior official from the
                current and previous administrations who had responsibility for topics covered in
                our mandate. We have sought to be independent, impartial, thorough, and nonpartisan.
                From the outset, we have been committed to share as much of our investigation as we
                can with the American people. To that end, we held 19 days of hearings and took
                public testimony from 160 witnesses.
            Our aim has not been to assign individual blame. Our aim has been to provide the
                fullest possible account of the events surrounding 9/11 and to identify lessons
                learned.
            We learned about an enemy who is sophisticated, patient, disciplined, and lethal. The
                enemy rallies broad support in the Arab and Muslim world by demanding redress of
                political grievances, but its hostility toward us and our values is limitless. Its
                purpose is to rid the world of religious and political pluralism, the plebiscite,
                and equal rights for women. It makes no distinction between military and civilian
                targets. Collateral damage is not in its lexicon.
            We learned that the institutions charged with protecting our borders, civil aviation,
                and national security did not understand how grave this threat could be, and did not
                adjust their policies, plans, and practices to deter or defeat it. We learned of
                fault lines within our government-between foreign and domestic intelligence, and
                between and within agencies. We learned of the pervasive problems of managing and
                sharing information across a large and unwieldy government that had been built in a
                different era to confront different dangers.
            At the outset of our work, we said we were looking backward in order to look forward.
                We hope that the terrible losses chronicled in this report can create something
                positive-an America that is safer, stronger, and wiser. That September day, we came
                together as a nation. The test before us is to sustain that unity of purpose and
                meet the challenges now confronting us. We need to design a balanced strategy for
                the long haul, to attack terrorists and prevent their ranks from swelling while at
                the same time protecting our country against future attacks. We have been forced to
                think about the way our government is organized. The massive departments and
                agencies that prevailed in the great struggles of the twentieth century must work
                together in new ways, so that all the instruments of national power can be combined.
                Congress needs dramatic change as well to strengthen oversight and focus
                accountability.
            As we complete our final report, we want to begin by thanking our fellow
                Commissioners, whose dedication to this task has been profound. We have reasoned
                together over every page, and the report has benefited from this remarkable
                dialogue. We want to express our considerable respect for the intellect and judgment
                of our colleagues, as well as our great affection for them.
            We want to thank the Commission staff. The dedicated professional staff, headed by
                Philip Zelikow, has contributed innumerable hours to the completion of this report,
                setting aside other important endeavors to take on this all-consuming assignment.
                They have conducted the exacting investigative work upon which the Commission has
                built. They have given good advice, and faithfully carried out our guidance. They
                have been superb. We thank the Congress and the President. Executive branch agencies
                have searched records and produced a multitude of documents for us. We thank
                officials, past and present, who were generous with their time and provided us with
                insight. The PENTTBOM team at the FBI, the Director's Review Group at the CIA, and
                Inspectors General at the Department of Justice and the CIA provided great
                assistance. We owe a huge debt to their investigative labors, painstaking attention
                to detail, and readiness to share what they have learned. We have built on the work
                of several previous Commissions, and we thank the Congressional Joint Inquiry, whose
                fine work helped us get started. We thank the City of New York for assistance with
                documents and witnesses, and the Government Printing Office and W.W. Norton
                & Company for helping to get this report to the broad public.
            We conclude this list of thanks by coming full circle: We thank the families of 9/11,
                whose persistence and dedication helped create the Commission. They have been with
                us each step of the way, as partners and witnesses. They know better than any of us
                the importance of the work we have undertaken.
            We want to note what we have done, and not done. We have endeavored to provide the
                most complete account we can of the events of September 11, what happened and why.
                This final report is only a summary of what we have done, citing only a fraction of
                the sources we have consulted. But in an event of this scale, touching so many
                issues and organizations, we are conscious of our limits. We have not interviewed
                every knowledgeable person or found every relevant piece of paper. New information
                inevitably will come to light. We present this report as a foundation for a better
                understanding of a landmark in the history of our nation.
            We have listened to scores of overwhelming personal tragedies and astounding acts of
                heroism and bravery. We have examined the staggering impact of the events of 9/11 on
                the American people and their amazing resilience and courage as they fought back. We
                have admired their determination to do their best to prevent another tragedy while
                preparing to respond if it becomes necessary. We emerge from this investigation with
                enormous sympathy for the victims and their loved ones, and with enhanced respect
                for the American people. We recognize the formidable challenges that lie ahead.
            We also approach the task of recommendations with humility. We have made a limited
                number of them. We decided consciously to focus on recommendations we believe to be
                most important, whose implementation can make the greatest difference. We came into
                this process with strong opinions about what would work. All of us have had to
                pause, reflect, and sometimes change our minds as we studied these problems and
                considered the views of others. We hope our report will encourage our fellow
                citizens to study, reflect-and act.
            Thomas H. Kean, chair
            Lee H. Hamilton, vice chair
        
    
(END)
```
![Screenshot 2024-02-11 at 6 16 36 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/6fa0a4cb-9405-409e-a2e9-9718e684655e)

In this situation, I want to quickly scan through the file for specific information, having fewer empty lines can speed up the process by reducing the amount of scrolling required to navigate through the file.


Example2:
```java
 For people who received their introduction to cancer genetics in college in the first
        half of the 1990s, everything looked simple and straightforward. It was the stuff you could
        explain to sincerely interested relatives who wanted to know what you were spending your
        time on. There were oncogenes and there were tumour suppressor genes. Oncogenes were
        overactive genes and proteins that somehow caused cancer because they were overactive;
        therefore, they were dominant. Tumour suppressor genes were genes that would normally
        prevent a tumour from happening and that needed to be inactivated for a tumour to start to
        form; both copies of a tumour suppressor gene had to be inactivated, and the mutation was
        recessive. If inactivation of these genes is a random process, it was understandable that
        people who inherit an inactivated copy of a tumour suppressor gene had a higher risk of
        developing the associated form(s) of cancer than people born with two normal copies, as
        postulated in Alfred Knudson's (1971) two-hit model. And, indeed, it was shown that in the
        tumours in these predisposed patients, the remaining wild-type copy of the tumour
        suppressor gene was lost, a process referred to as loss of heterozygosity.
        For me, in 1998 things started to change. Venkatachalam et al. (1998) published a paper
        in the 
        EMBO Journal describing a detailed study of tumours in mice lacking one
        copy of the p53 tumour suppressor gene (
        Trp53 ). This gene is known to be the most mutated gene in human cancer
        and its function to be central to many processes that are involved in the cellular
        prevention of cancer. Mice lacking both copies of this gene are for the most part viable,
        but succumb to cancer (mainly thymic lymphomas) at three to five months of age (Donehower
        et al. 1992). Mice born with one copy of the 
        Trp53 gene start to develop cancer at around nine months, and incidence
        increases with age.
        In their study, Venkatachalam and colleagues analysed an impressive group of 217 
        Trp53
        +/− mice of controlled genetic background and followed the fate of the 
        Trp53 wild-type allele in the tumours. According to the two-hit model, it
        was expected that in these tumours this copy would have been lost or inactivated. However,
        this turned out not to be the case. Half of the tumours from mice younger than 18 months
        were found to have retained the wild-type copy of 
        Trp53 , a number that increased to 85% in mice older than 18 months. In
        two tumours, the researchers sequenced the complete coding region of the remaining
        wild-type allele and showed it was structurally intact. To exclude the possibility of
        downregulation or inactivation at the level of protein expression, they irradiated
        tumour-bearing mice prior to sacrifice, a treatment known to increase p53 protein levels
        via posttranslational mechanisms. Their data showed the retained wild-type allele in these
        tumours was expressed normally and suggested it had a normal wild-type conformation.
        Next, the authors did a rigorous test of different functions of the p53 protein. They
        first tested whether the tumours showed amplification of Mdm2. This protein, whose
        expression is regulated by p53, stimulates breakdown of p53, thereby forming a negative
        feedback mechanism that keeps p53 levels low. Some tumours therefore amplify the 
        Mdm2 gene as a means of inactivating p53. However, this was not found in
        the tumours from the 
        Trp53
        +/− mice. Subsequently, the researchers tested to what extent the
        retained 
        Trp53 copy behaved normally. Irradiation of many tissues leads to
        p53-dependent apoptosis, and, indeed, in tumours that had retained the wild-type allele,
        irradiation did lead to an increase in apoptosis, whereas in tumours that had lost the
        wild-type allele, it did not.
        The p53 protein is known to function as a transcriptional regulator by either up- or
        down regulating target genes in response to different forms of cellular stress, including
        irradiation-induced DNA damage. The authors studied the expression of two p53-upregulated
        genes (
        Cdkn1a , which encodes p21, and 
        Mdm2 ) and one downregulated gene (
        Pcna ) in p53-positive tumours after irradiation and showed responses
        indicative of normal p53 function. Furthermore, it was shown that the p53 protein from the
        tumours was able to bind to a p53-binding DNA sequence in an in vitro setting. Finally,
        since it is known that p53 absence in tumours is correlated with chromosomal instability,
        Venkatachalam et al. (1998) used comparative genome hybridisation to compare this feature
        between p53-negative and p53-positive tumours and found a 5-fold greater stability in the
        latter.
        In short, this paper clearly showed that, at least in mice, in many 
        Trp53
        +/− tumours the wild-type allele of 
        Trp53 is not only retained, but also appears to function normally. This
        strongly suggested that a decrease of dosage in p53 is already sufficient for
        tumourigenesis, a phenomenon referred to as haploinsufficiency. Shortly before, the group
        of Moshe Oren (Gottlieb et al. 1997) had shown that a 
        Trp53
        +/− background leads to a greater than 50% reduction in p53 activity
        using a p53-responsive 
        lacZ reporter gene in transgenic mice. Venkatachalam and colleagues
        suggested the strong concentration dependence of p53 function could be explained by the
        fact that p53 functions as a tetramer. A 50% decrease in p53 monomers can easily be
        imagined to result in a greater than 50% decrease in functional tetramers, which in turn
        increases the chances of these cells becoming cancerous.
        This paper by Venkatachalam et al. (1998) made me realise how important it is to remain
        critical, even of long-established theories and models. Since then, haploinsufficient
        mechanisms have been described in more tumour suppressor genes in humans and mice (reviewed
        in Fodde and Smits 2002). For instance, in a recent paper in
        PLoS Biology , Trotman et al. (2003) used mouse models to describe how
        the dosage of the 
        Pten tumour suppressor gene influences the occurrence of prostate cancer.
        Further genes have been described with other unexpected roles in the tumourigenic process.
        There is a long-standing debate in the literature about the number and role of mutations in
        a tumour, and without going into the details, it is clear that haploinsufficient mechanisms
        for tumour suppressor genes will greatly influence the statistics on which these
        discussions are based. At a time when microarray analysis has become a standard experiment
        and the many thousands of changes in tumour cells are analysed across the whole genome, it
        is important to keep in mind that the correct interpretation of this wealth of information
        might be more complicated than the widely accepted models would have us believe.
```
![Screenshot 2024-02-11 at 6 13 40 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/f47f550c-ed76-4b95-9331-fde447511579)


In this situation, by using less -s, the content of the file is condense. `less -s` can provide a more compact and concise view of the content, allowing me to see more information on the screen at once, 
which saved a lot of time and space.

![Screenshot 2024-02-11 at 8 44 11 PM](https://github.com/LC0229/cse15l-lab-reports/assets/156004283/de94a5dd-a766-4bcd-afd7-96222d0a4573)


*Case4 less -X

Keep the content of the file on the terminal, instead of quitting it by the end.


```java
chenshengrui@zuis-MacBook-Pro technical % less -X  911report/preface.txt   

    
        
            PREFACE
            We present the narrative of this report and the recommendations that flow from it to
                the President of the United States, the United States Congress, and the American
                people for their consideration. Ten Commissioners-five Republicans and five
                Democrats chosen by elected leaders from our nation's capital at a time of great
                partisan division-have come together to present this report without dissent.
            We have come together with a unity of purpose because our nation demands it.
                September 11, 2001, was a day of unprecedented shock and suffering in the history of
                the United States. The nation was unprepared. How did this happen, and how can we
                avoid such tragedy again?
            To answer these questions, the Congress and the President created the National
                Commission on Terrorist Attacks Upon the United States (Public Law 107-306, November
                27, 2002).
            Our mandate was sweeping. The law directed us to investigate "facts and circumstances
                relating to the terrorist attacks of September 11, 2001," including those relating
                to intelligence agencies, law enforcement agencies, diplomacy, immigration issues
                and border control, the flow of assets to terrorist organizations, commercial
                aviation, the role of congressional oversight and resource allocation, and other
                areas determined relevant by the Commission. In pursuing our mandate, we have
                reviewed more than 2.5 million pages of documents and interviewed more than 1,200
                individuals in ten countries. This included nearly every senior official from the
                current and previous administrations who had responsibility for topics covered in
                our mandate. We have sought to be independent, impartial, thorough, and nonpartisan.
                From the outset, we have been committed to share as much of our investigation as we
                can with the American people. To that end, we held 19 days of hearings and took
                public testimony from 160 witnesses.
            Our aim has not been to assign individual blame. Our aim has been to provide the
                fullest possible account of the events surrounding 9/11 and to identify lessons
                learned.
chenshengrui@zuis-MacBook-Pro technical %
```
We can simply see the content of the file in the process of typing command, we do not have to go to the content screen and quit for it. It allows me to work continuously when I'm doing work.



Example2:
