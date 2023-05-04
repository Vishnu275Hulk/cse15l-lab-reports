# Lab Report 3

This lab report will be demonstrating four different ways of using the command `grep` on various files. 
`grep <<string>> <<file>>` searches a file or files for the given string and prints the matching lines.
There are several command-line options of `grep` that print results much different than its default setting. Here are four of such examples.

# Option 1: `grep -n` 
`grep -n <<string>> <<file>>` prints the lines matching the given string along with the line numbers in the file. 
This command is especially useful when you want to pinpoint a certain line where a given string is present.

The following command prints all the lines with the word "San Diego" along with the line numbers in the file.
In case a cop reading this report would like find the line number that references San Diego and Karachi (line 45), 
this gives the required information pretty quickly thus saving their time.

```
[cs15lsp23aj@ieng6-203]:technical:172$ grep -n "San Diego" 911report/chapter-7.txt 
44:                to have steered the two to San Diego on the basis of his own research, which
45:                supposedly included thumbing through a San Diego phone book acquired at a Karachi
91:                somewhat suspect. (He likewise denied knowing Omar al Bayoumi-a man from San Diego
106:                told us that they had driven up from San Diego earlier that day so that Bayoumi
116:                them how pleasant San Diego was and offered to help them settle there. The two pairs
139:                from San Diego. It is certainly possible that he has dissembled about some aspects
146:                extremists. The Move to San Diego By February 4, Hazmi and Mihdhar had come to San
168:                Los Angeles to San Diego, but did not say when this occurred. We have been unable to
172:                terrorist plans after they arrived in San Diego, when they told him they planned to
183:                not know when or how Hazmi and Mihdhar first came to San Diego. We do know that on
184:                February 4, they went to the Islamic Center of San Diego to find Omar al Bayoumi and
217:                met at a mosque in San Diego. According to the homeowner, the future hijackers moved
219:                San Diego to return to Yemen. Hazmi, on the other hand, stayed at this house for the
223:            While in San Diego, Hazmi and Mihdhar played the part of recently arrived foreign
226:                of San Diego, which was only a stone's throw from the apartment where they first
235:                operatives' critical first weeks in San Diego, Mohdar Abdullah helped them.
242:            Abdullah has emerged as a key associate of Hazmi and Mihdhar in San Diego. Detained
251:                adjust to life in San Diego. Some held extremist beliefs or were well acquainted
258:                learn English and taking over the operatives' first apartment in San Diego after
262:            Another potentially significant San Diego contact for Hazmi and Mihdhar was Anwar
267:                to San Diego. Hazmi and Mihdhar reportedly respected Aulaqi as a religious figure
276:            Aulaqi left San Diego in mid-2000, and by early 2001 had relocated to Virginia. As we
285:                mosque. The al Qaeda operatives lived openly in San Diego under their true names,
296:            A pilot they consulted at one school, the Sorbi Flying Club in San Diego, spoke
310:                and arranged his return to Yemen. According to KSM, Mihdhar was bored in San Diego
319:                in the United States. Mihdhar's decision to strand Hazmi in San Diego enraged KSM,
351:            On December 8, 2000, Hani Hanjour arrived in San Diego, having traveled from Dubai
353:                know where Hanjour stayed; a few days later, both men left San Diego. Before
358:                to San Diego soon, and he and Hanjour drove off.
360:            Hazmi did not sever all contact with his friends in San Diego. According to Abdullah,
361:                after Hazmi left San Diego in December 2000, he telephoned Abdullah twice: in
366:                following Hazmi's departure from San Diego, he emailed his housemate three times,
512:                his trip. On December 8, Hanjour traveled to San Diego. His supposed destination was
515:                earlier, he joined Nawaf al Hazmi in San Diego.
517:            Hazmi and Hanjour left San Diego almost immediately and drove to Arizona. Settling in
589:                with whom Hazmi had spent time at the Rabat mosque in San Diego. Aulaqi had moved to
590:                Virginia in January 2001. He remembers Hazmi from San Diego but has denied having
942:                had abandoned Hazmi in San Diego in June 2000 and returned to his family in Yemen.
```

The following command prints all the lines and line numbers containing the word "Pentagon".
If someone wants to find out the line number where Pentagon and Wolfowitz are referenced, this command would be worthwhile. 

```
[cs15lsp23aj@ieng6-203]:technical:179$ grep -n "Pentagon" 911report/chapter-10.txt 
50:                been implemented. 9 The Pentagon had been struck; the White House or the Capitol had
56:                still-smoldering Pentagon. At 8:30 that evening, President Bush addressed the nation
338:                plan the Pentagon had begun developing in November 2000 as an addition to the strike
403:                Hanjour's high-speed dive into the Pentagon. He told us he recalled Iraqi support
478:            Within the Pentagon, Deputy Secretary Wolfowitz continued to press the case for
498:            Shelton told us the administration reviewed all the Pentagon's war plans and
543:                President had a message for the Pentagon:"The hour is coming when America will act,
```

# Option 2: `grep -l`
`grep -l <<string>> <<path>>` prints all the files containing the given string in the given directory/path.
This command saves you a lot of time when you want to pinpoint the location of a certain string.

The following command prints all the files in the `911report` directory that contain the word "San Diego".
If someone wants to know what happened in San Diego but there are hundreds of files to scan through, 
then this command narrows down the files they would need to search.

```
[cs15lsp23aj@ieng6-203]:technical:182$ grep -l "San Diego" 911report/*.txt
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
```

This command prints all the files in the `plos` directory containing the word "bees".
When someone wants to find information about bees in a given directory, this is the command for them.

```
[cs15lsp23aj@ieng6-203]:technical:188$ grep -l "bees" plos/*.txt                    
plos/journal.pbio.0020043.txt
plos/journal.pbio.0020216.txt
plos/journal.pbio.0020350.txt
plos/journal.pbio.0030137.txt
plos/pmed.0020209.txt
```

# Option 3: `grep -w`
By default, grep matches the given string even if it is found as a substring in a file.
`grep -w <<string>> <<file>>` matches words in their entirety excluding the substrings.
This command gives a more precise result when asked to search for a word.

The following command searches for the word "The". If we executed this command without implementing -w, 
then it woulld've printed all the lines with the substring "The" which includes words like "They", "There", etc.
The command gives a more precise and accurate output.

```
[cs15lsp23aj@ieng6-203]:technical:189$ grep -w "The" 911report/chapter-7.txt 
                Hazmi, Mihdhar, and Khallam could meet in private. The identity of Khallam and his
            The circumstantial evidence makes Thumairy a logical person to consider as a possible
                them how pleasant San Diego was and offered to help them settle there. The two pairs
            The object of considerable media speculation following 9/11, he lives now in Saudi
                extremists. The Move to San Diego By February 4, Hazmi and Mihdhar had come to San
                Hazmi and Mihdhar were planning a terrorist attack. The stories attributed to
                Mihdhar became belligerent. The landlord remembers him "ranting and raving" as if he
                jailhouse admissions concerning the 9/11 operatives. The Department of Justice
                scholarship. We do not know how or when Hazmi and Mihdhar first met Aulaqi. The
                mosque. The al Qaeda operatives lived openly in San Diego under their true names,
            The housemate who rented the room to Hazmi and Mihdhar during 2000 is an apparently
            The Hamburg Pilots Arrive in the United States
            The Hamburg operatives paid for their flight training primarily with funds wired from
                to Germany to visit his girlfriend, Aysel Senguen. The two traveled to Paris before
            The Fourth Pilot: Hani Hanjour
            The fact that Hanjour spent so much time in Arizona may be significant. A number of
                not good enough. The instructor advised him to discontinue but Hanjour said he could
            The three pilots in Florida continued with their training. Atta and Shehhi finished
                Jarrah's trips and Senguen's visit. The other operatives had broken off regular
                him missing to the UAE government. The UAE embassy in turn contacted the Hamburg
                in Hamburg. The UAE government then told the Hamburg police they could call off the
                Hazmi, Saeed al Ghamdi, Ahmad al Haznawi, and Ahmed al Nami. The remaining recruit,
                they found. The muscle hijackers came from a variety of educational and societal
            The three remaining muscle hijackers from Saudi Arabia were Satam al Suqami, Majed
                clerics as a "terrorist factory." The province is at the very heart of the strict
            The majority of these Saudi recruits began to break with their families in late 1999
                Afghanistan. These statements might be true or cover stories. The four recruits from
                selecting the planes operation participants. The second most important criterion was
                were chosen to avoid raising alerts during travel. The al Qaeda training camp head
                not told details about the operation. The majority of the Saudi muscle hijackers
                Afghanistan for special training in late 2000 to early 2001. The training reportedly
                knife to prepare to use knives during the hijackings. The recruits learned to focus
                to worry about seizing control over the rest of the plane later. The operatives were
                via the UAE. The safehouse was run by al Qaeda operative Abd al Rahim Ghulum
                The future hijackers usually arrived in groups of two or three, staying at the safe
                house for as long as two weeks. The facilitator has identified each operative whom
            The muscle hijackers began arriving in the United States in late April 2001. In most
            The muscle hijackers supplied an infusion of funds, which they carried as a mixture
            The hijackers made extensive use of banks in the United States, choosing both
            The last muscle hijacker to arrive was Khalid al Mihdhar. As mentioned earlier, he
                the arrival of a group during the same time period. The travel of this group was
            The majority settled in Florida. Some opened bank accounts, acquired mailboxes, and
                where they had reservations at the Bahamas Princess Resort. The two were turned away
            The three Hamburg pilots-Atta, Shehhi, and Jarrah-took the first of their
            The Meeting in Spain
                from his room, most likely to coordinate with Binalshibh. The next day, Atta rented
                problems carrying box cutters on cross-country surveillance flights. The best time
            The conversation covered various topics. For example, Jarrah was to send Binalshibh
            The most significant part of the mid-July conversation concerned Jarrah's troubled
                his disagreement with Atta apparently resolved. The operatives began their final
                days in the area before returning to Florida on July 30. The month of August was
                frequent practice flights on small rented aircraft. The operatives also began to
                envisioned for May 2001. The second time he was urged to launch the attacks early
                the latter date in two letters stressing the need to attack early. The second letter
                had a different view. The Taliban leaders put their main emphasis on the year's
                disagreed, Bin Ladin persisted. The attacks went forward.
            The story of dissension within al Qaeda regarding the 9/11 attacks is probably
                incomplete. The information on which the account is based comes from sources who
                The general Taliban offensive against the Northern Alliance would rely on al
                    plot to assassinate the Northern Alliance leader, Ahmed Shah Massoud. The
            But on September 9, the Massoud assassination took place. The delayedTaliban
            The hijackers targeting American Airlines Flight 77, to depart from Dulles, migrated
                and Atta was seen with him at his hotel. The next day, Atta picked up Omari at
                to Boston to connect to American Airlines Flight 11. The two spent their last night
            The plan that started with a proposal by KSM in 1996 had evolved to overcome numerous
```

This command prints all the lines with the word "odor". By default, grep would print substrings such as "odorant", "odors", etc. 
along with the given string. However, if we only wanted the word "odor" this command is quite useful.

```
[cs15lsp23aj@ieng6-203]:technical:204$ grep -w  "odor" plos/journal.pbio.0030137.txt 
        study by Guerrieri et al. [8] on odor space in honeybees in this issue is an excellent
        receptor cell, so that there are indeed about 1,000 different odor receptor cell types in
        proteins that bind odor molecules are also expressed in the axon terminals of the receptor
        aldehydes, and ketones. Distances between odor loci in this three-dimensional space
        Take mixtures of different stimuli, for example. If odor perception followed rules
        On the other hand, are odor mixtures simply perceived as a compound entity with distinct
        assessments of odor similarities: bees respond as if they find odor A more similar to
        trained odor B than they find B to trained odor A. It will be difficult to represent these
        These phenomena indicate that odor perception cannot be as easily visualized in a
        available to the neuronal centers that ultimately “decide” on odor similarity, and
```

# Option 4: `grep -R`
`grep -R` searches the entire directory for the given string and then prints the lines as part of the files.
This saves a lot of time in finding out which files contain the desired string, especially when the directory has hundreds of files.

This command prints all the files and lines with the organization "Al Qaeda".
This saves an enormous amount of time because without this command one would have to search all individual files.

```
[cs15lsp23aj@ieng6-203]:technical:208$ grep -R "Al Qaeda" 
911report/chapter-11.txt:                State were largely ineffective. Al Qaeda and terrorism was just one more priority
911report/chapter-11.txt:                prevented the 9/11 attacks. Al Qaeda adapted to the failure of some of its
911report/chapter-12.txt:            Vague goals match an amorphous picture of the enemy. Al Qaeda and its affiliates are
911report/chapter-12.txt:            Al Qaeda also exploited relatively lax internal security environments in Western
911report/chapter-13.3.txt:            20. Rohan Gunaratna, Inside Al Qaeda: Global Network ofTerror (Columbia Univ. Press,
911report/chapter-13.3.txt:            24. See Abdullah Azzam, "Al Qaeda al Sulbah" (The solid foundation), Al Jihad, Apr.
911report/chapter-13.3.txt:                Gunaratna, Inside Al Qaeda, p. 23.
911report/chapter-13.3.txt:            29. Gunaratna, Inside Al Qaeda, pp. 25-27; DOD document, "Union Agreement between
911report/chapter-13.3.txt:            34. Gunaratna, Inside Al Qaeda, p. 34.
911report/chapter-13.3.txt:                Nov. 29, 2001, p. 1 and appendix B; see also Gunaratna, Inside Al Qaeda, pp.
911report/chapter-13.3.txt:                Intelligence report, Al Qaeda Targeting Study of U.S. Embassy Nairobi, prepared 23
911report/chapter-13.3.txt:            4 Responses to Al Qaeda's Initial Assaults
911report/chapter-13.3.txt:                Way While Al Qaeda Funds Flowed," Los Angeles Times, Jan. 20, 2002, p. A1. Enforcing
911report/chapter-13.3.txt:                Conference, prepared for Berger, Nov. 30, 1999. 5 Al Qaeda Aims at the American
911report/chapter-13.4.txt:            21. Rohan Gunaratna, Inside Al Qaeda: Global Network of Terror (Columbia Univ. Press,
911report/chapter-13.4.txt:                Intelligence report, interrogation of Hambali, Mar. 5, 2004. Al Qaeda began
911report/chapter-13.4.txt:                Al Qaeda travel issues, Jan. 2004, p. 1. On the role of KSM, see, e.g., Intelligence
911report/chapter-13.4.txt:                2002. Al Qaeda also relied on outside travel facilitators, including fraudulent
911report/chapter-13.4.txt:                Al Qaeda travel issues, Jan. 2004.
911report/chapter-13.4.txt:                CIA analytic report, Al Qaeda travel issues, Jan. 2004, pp.1,3, 19. A detainee has
911report/chapter-13.4.txt:                cachets. CIA analytic report, Al Qaeda travel issues, Jan. 2004, p. 1.
911report/chapter-13.4.txt:                2002-40132HCX, Jan. 17, 2003; CIA analytic report, Al Qaeda Financial Network, CTC
911report/chapter-13.4.txt:                report, "Allegations of Al Qaeda Trafficking in Conflict Diamonds," July 18, 2003;
911report/chapter-13.4.txt:            5. Ibid. On Hoshar and Hijazi, see Jason Burke, Al Qaeda: Casting a Shadow of Terror
911report/chapter-13.4.txt:                Pincus and Dan Eggen,"Al Qaeda Link to Iraq May Be Confusion over Names," Washington
911report/chapter-13.4.txt:                the problem. Al Qaeda money flows depended on an informal network of hawalas and
911report/chapter-13.4.txt:            58. Al Qaeda figures at the university or in Tucson included Mubarak al Duri,
911report/chapter-13.4.txt:                United States. See CIA analytic report, Al Qaeda Travel Issues, CTC 2004-40002H,
911report/chapter-13.5.txt:                Against Al Qaeda," Feb. 21, 2001 (provided as background for Tenet meetings with
911report/chapter-2.txt:            Al Qaeda helped Jemaah Islamiya (JI), a nascent organization headed by Indonesian
911report/chapter-2.txt:            Al Qaeda leaders set up a Nairobi cell and used it to send weapons and trainers to
911report/chapter-2.txt:                set the price at $1.5 million, which did not deter Bin Ladin. Al Qaeda
911report/chapter-2.txt:                long, and one thought he could pronounce it genuine. Al Qaeda apparently purchased
911report/chapter-2.txt:                in Afghanistan a freedom of movement that he had lacked in Sudan. Al Qaeda members
911report/chapter-2.txt:                of official Afghan Ministry of Defense license plates. Al Qaeda also used the Afghan
911report/chapter-2.txt:            Al Qaeda continued meanwhile to collaborate closely with the many Middle Eastern
911report/chapter-2.txt:                snake." Al Qaeda's role in organizing terrorist operations had also changed. Before
911report/chapter-2.txt:                they began to form a plan. Al Qaeda had begun developing the tactical expertise for
911report/chapter-5.txt:                share. Al Qaeda associate Abu Zubaydah has expressed more qualified admiration for
911report/chapter-5.txt:            Al Qaeda's success in fostering terrorism in Southeast Asia stems largely from its
911report/chapter-5.txt:                KSM, Hambali soon began dealing with Atef as well. Al Qaeda began funding JI's
911report/chapter-5.txt:                bomb-making materials and other supplies. Al Qaeda would underwrite operations,
911report/chapter-5.txt:            Al Qaeda appears to have relied on a core group of financial facilitators who raised
911report/chapter-5.txt:                their donations. Al Qaeda and its friends took advantage of Islam's strong calls for
911report/chapter-5.txt:            Al Qaeda also collected money from employees of corrupt charities.
911report/chapter-5.txt:            Al Qaeda also sought money from wealthy donors in other Gulf states.
911report/chapter-5.txt:            Al Qaeda frequently moved the money it raised by hawala, an informal and ancient
911report/chapter-5.txt:                annual operating budget. Al Qaeda funded salaries for jihadists, training camps,
911report/chapter-5.txt:            Al Qaeda has been alleged to have used a variety of illegitimate means, particularly
911report/chapter-5.txt:                significance. Al Qaeda had many avenues of funding. If a particular funding source
911report/chapter-6.txt:            Al Qaeda, and Bin Ladin himself, did have at least one operation of their very own in
911report/chapter-6.txt:            Al Qaeda's "planes operation" was also coming along. In January 2000, the United
911report/chapter-6.txt:                many extremists to travel to Afghanistan for training and jihad. Al Qaeda members
911report/chapter-7.txt:                Arabia itself. Al Qaeda recruiters, certain clerics, and-in a few cases-family
911report/chapter-7.txt:                Hezbollah, which is based mainly in southern Lebanon and Beirut. Al Qaeda members
911report/chapter-7.txt:                operations outside Afghanistan. Al Qaeda's chief financial manager, Sheikh Saeed,
911report/chapter-8.txt:                targeted. Al Qaeda also released a new recruitment and fund-raising tape. Clarke
```

Th following command prints all the files and lines with the word "Alcohol".
This makes it easy to obtain the required file names, which would otherwise be cumbersome.

```
[cs15lsp23aj@ieng6-203]:technical:210$ grep -R "Alcohol"
911report/chapter-13.3.txt:            48. Treasury report, "1995 Highlights of The Bureau of Alcohol, Tobacco and
911report/chapter-13.5.txt:                Lessons Learned from the 9/11 Attack on the Pentagon"). When the Bureau of Alcohol,
911report/chapter-13.5.txt:                of Alcohol, Tobacco, Firearms and Explosives (still abbreviated ATF); see ATF press
911report/chapter-3.txt:                Secret Service, the Customs Service, and the Bureau of Alcohol, Tobacco, and
911report/chapter-3.txt:            The Bureau of Alcohol, Tobacco, and Firearms was used on occasion by the FBI as a
911report/chapter-9.txt:                National Medical ResponseTeam, the Bureau of Alcohol, Tobacco, and Firearms, and
biomed/1471-213X-3-4.txt:          0.5 ml Isopropyl Alcohol, and centrifuged at 12000 rpm
biomed/1471-2156-3-22.txt:          2-pack year smoking history was reported. Alcohol
biomed/1471-2210-1-2.txt:        Alcohol has been associated with NTDs [ 11 ] and is known
biomed/1471-2334-3-11.txt:        might influence the length of hospital stay. Alcohol and
biomed/1471-2458-2-6.txt:          and any prescribed medications. Alcohol was given under
biomed/1471-2458-2-6.txt:          arduous work in hot conditions. Alcohol, tea or coffee
biomed/1471-2466-2-3.txt:          Alcohol intake
biomed/1471-2466-2-3.txt:          standardization. Alcohol consumption was assessed for the
biomed/1471-2466-2-3.txt:          1 % and FVC%. Alcohol intake from beer
biomed/1471-2466-2-3.txt:          with pulmonary function. Alcohol intake from wine was
biomed/1471-2466-2-3.txt:        1 and FVC%. Alcohol from beer and liquor
biomed/1478-7954-1-3.txt:          5 (Alcohol index) 
biomed/1478-7954-1-3.txt:          5 (Alcohol index) 
biomed/1478-7954-1-3.txt:          4 (Alcohol index) 
biomed/1478-7954-1-3.txt:          4 (Alcohol index) 
biomed/bcr605.txt:            Alcohol consumption
biomed/bcr605.txt:        Alcohol use has been increasingly associated with both
biomed/gb-2001-2-7-research0025.txt:          genomic sequences. Alcohol dehydrogenases (1, 2, 3, 4, 5
government/Alcohol_Problems/DraftRecom-PDF.txt:become research priorities. Alcohol and injury, as well as brief
government/Alcohol_Problems/Session2-PDF.txt:Identifying ED Patients with Alcohol Problems
government/Alcohol_Problems/Session2-PDF.txt:Alcohol problems defined
government/Alcohol_Problems/Session2-PDF.txt:Alcohol problems designate a spectrum from risk behavior to
government/Alcohol_Problems/Session2-PDF.txt:Institute on Alcohol Abuse and Alcoholism (NIAAA) defines at-risk
government/Alcohol_Problems/Session2-PDF.txt:The MAST (Michigan Alcohol-Screening Test), developed in 1971 as
government/Alcohol_Problems/Session2-PDF.txt:SAAST (Self-Administered Alcoholism Screening Test) was
government/Alcohol_Problems/Session2-PDF.txt:drinkers. WHO developed the AUDIT (Alcohol Use Disorder
government/Alcohol_Problems/Session2-PDF.txt:Rapid Alcohol Assessment Screen (RAPS4). Cherpitel screened an ED
government/Alcohol_Problems/Session2-PDF.txt:Alcohol concentration
government/Alcohol_Problems/Session2-PDF.txt:4. National Institute on Alcohol Abuse and Alcoholism. The
government/Alcohol_Problems/Session2-PDF.txt:Physician's Guide to Helping Patients with Alcohol Problems.
government/Alcohol_Problems/Session2-PDF.txt:the CAGE, the Brief Michigan Alcoholism Screening Test, and the
government/Alcohol_Problems/Session2-PDF.txt:Alcohol Use Disorders Identification Test in screening trauma
government/Alcohol_Problems/Session2-PDF.txt:regions of the country. Alcohol Clin Exp Res 1997;21:1391-7.
government/Alcohol_Problems/Session2-PDF.txt:Clifford P. Alcohol use among subcritically injured emergency
government/Alcohol_Problems/Session2-PDF.txt:alcohol-related problems in general practice. J Stud Alcohol
government/Alcohol_Problems/Session2-PDF.txt:with the Alcohol Use Disorders Identification Test (AUDIT) in an
government/Alcohol_Problems/Session2-PDF.txt:screening in an ambulatory care setting. J Stud Alcohol
government/Alcohol_Problems/Session2-PDF.txt:screening questionnaire. Alcohol 1991;26:81-91.
government/Alcohol_Problems/Session2-PDF.txt:version of the Michigan Alcoholism Screening Test. Am J Psychiatry
government/Alcohol_Problems/Session2-PDF.txt:27. Selzer M. The Michigan Alcoholism Screening Test: the quest
government/Alcohol_Problems/Session2-PDF.txt:Short Michigan Alcoholism Screening Test (SMAST). J Stud Alcohol
government/Alcohol_Problems/Session2-PDF.txt:analysis of the Self-Administered Alcoholism Screening Test.
government/Alcohol_Problems/Session2-PDF.txt:Alcohol Clin Exp Res 1987;11:269-73.
government/Alcohol_Problems/Session2-PDF.txt:30. Davis L, Jr., Morse R. Self-Administered Alcoholism
government/Alcohol_Problems/Session2-PDF.txt:computer-administered formats. Alcohol Clin Exp Res
government/Alcohol_Problems/Session2-PDF.txt:31. Saunders J, Aasland O, Amundsen A, Grant M. Alcohol
government/Alcohol_Problems/Session2-PDF.txt:With Harmful Alcohol Consumption, I. Addiction 1993;88:349-62.
government/Alcohol_Problems/Session2-PDF.txt:Development of the Alcohol Use Disorders Identification Test
government/Alcohol_Problems/Session2-PDF.txt:pregnancy risk-drinking. Alcohol Clin Exp Res 1994;18:1156-61.
government/Alcohol_Problems/Session2-PDF.txt:drinking in the emergency room: the RAPS4. Rapid Alcohol Problems
government/Alcohol_Problems/Session2-PDF.txt:Screen. J Stud Alcohol 2000;61:447-9.
government/Alcohol_Problems/Session2-PDF.txt:in an emergency room population. J Stud Alcohol 1998;59:420-6.
government/Alcohol_Problems/Session2-PDF.txt:the CAGE, the Brief Michigan Alcohol Screening Test, and the
government/Alcohol_Problems/Session2-PDF.txt:Alcohol Use Disorders Identification Test in screening trauma
government/Alcohol_Problems/Session2-PDF.txt:dependence in the emergency room. Alcohol Clin Exp Res
government/Alcohol_Problems/Session2-PDF.txt:Alcohol 1995;56:695-700.
government/Alcohol_Problems/Session2-PDF.txt:41. Bradley KA, Boyd-Wickizer J, Powell SH, Burman ML. Alcohol
government/Alcohol_Problems/Session2-PDF.txt:Alcoholism. Criteria for the diagnosis of alcoholism. Am J
government/Alcohol_Problems/Session2-PDF.txt:instruments. Drug Alcohol Depend 1995;40:151-8.
government/Alcohol_Problems/Session2-PDF.txt:transferase (GGT), and mean corpuscular volume (MCV). Alcohol Clin
government/Alcohol_Problems/Session2-PDF.txt:Alcohol. 1998;33:304-9.
government/Alcohol_Problems/Session2-PDF.txt:Alcohol Clin Exp Res 1998;22:892-6.
government/Alcohol_Problems/Session2-PDF.txt:Alcoholism screening in the elderly. J Am Geriatr Soc
government/Alcohol_Problems/Session2-PDF.txt:62. Bercsi S, Brickner P, Saha D. Alcohol use and abuse in the
government/Alcohol_Problems/Session2-PDF.txt:Alcohol Depend 1993;33:139-49.
government/Alcohol_Problems/Session2-PDF.txt:64. Fink A, Hays RD, Moore AA, Beck JC. Alcohol-related
government/Alcohol_Problems/Session3-PDF.txt:Intervening with Alcohol Problems
government/Alcohol_Problems/Session3-PDF.txt:additional treatment or self-help groups like Alcoholics Anonymous.
government/Alcohol_Problems/Session3-PDF.txt:admission and triage system of the emergency settings. Alcohol
government/Alcohol_Problems/Session3-PDF.txt:day treatment. Self-help groups like Alcoholics Anonymous, Women
government/Alcohol_Problems/Session3-PDF.txt:4. Maio RF, Waller PF, Blow FC, Hill EM, Singer KM. Alcohol
government/Alcohol_Problems/Session3-PDF.txt:5. Whiteman PJ, Hoffman RS, Goldfrank LR. Alcoholism in the
government/Alcohol_Problems/Session3-PDF.txt:10. Gentilello LM, Donovan DM, Dunn CW, Rivara FP. Alcohol
government/Alcohol_Problems/Session3-PDF.txt:11. Lowenstein SR, Weissberg MP, Terry D. Alcohol intoxication,
government/Alcohol_Problems/Session3-PDF.txt:analysis of injury by cause among casualty. Alcohol Clin Exp
government/Alcohol_Problems/Session3-PDF.txt:18. Gentilello LM, Rivara FP, Donovan DM, et al. Alcohol
government/Alcohol_Problems/Session3-PDF.txt:department. Alcohol Alcohol
government/Alcohol_Problems/Session3-PDF.txt:abuse consultation team in a trauma center. J Stud Alcohol
government/Alcohol_Problems/Session3-PDF.txt:28. Hemphill C, Bennett BE, Watkins, BL. Alcoholism: the
government/Alcohol_Problems/Session3-PDF.txt:review of randomized controlled trials. Alcohol Alcohol
government/Alcohol_Problems/Session3-PDF.txt:36. Reyna TM, Hollis MW, Hulsebus RC. Alcohol-related trauma:
government/Alcohol_Problems/Session3-PDF.txt:37. Miller WR. Alcoholism: toward a better disease model.
government/Alcohol_Problems/Session3-PDF.txt:Mental Health Services Administration. Alcohol and Other Drug
government/Alcohol_Problems/Session3-PDF.txt:40. Soderstrom CA, Dailey JT, Kerns TJ. Alcohol and other
government/Alcohol_Problems/Session3-PDF.txt:for excessive drinkers: the need for caution. Alcohol Alcohol
government/Alcohol_Problems/Session3-PDF.txt:and lifestyle change. In: Howard G, editor. Issues in Alcohol Use
government/Alcohol_Problems/Session3-PDF.txt:Intervening with Alcohol Problems in
government/Alcohol_Problems/Session3-PDF.txt:of alcohol-related emergency room admission. J Stud Alcohol
government/Alcohol_Problems/Session3-PDF.txt:4. Cherpitel CJ. Alcohol, Injury, and risk-taking behavior:
government/Alcohol_Problems/Session3-PDF.txt:data from a national sample. Alcohol Clin Exp Res
government/Alcohol_Problems/Session3-PDF.txt:5. Dewey KE. Alcohol related attendances at the accident and
government/Alcohol_Problems/Session3-PDF.txt:6. Zink BJ, Maio RF. Alcohol use and trauma. Acad Emerg Med
government/Alcohol_Problems/Session3-PDF.txt:7. Maio RF. Alcohol and injury in the emergency department:
government/Alcohol_Problems/Session3-PDF.txt:of Alcohol-related Problems. Report on Phase II: A Randomized
government/Alcohol_Problems/Session3-PDF.txt:department. Alcohol Alcohol
government/Alcohol_Problems/Session3-PDF.txt:controlled trials. Alcohol Alcohol 1999;34:609-21.
government/Alcohol_Problems/Session3-PDF.txt:CW, et al. Alcohol interventions in a trauma center as a
government/Alcohol_Problems/Session3-PDF.txt:Alcoholics Anonymous session. Consequently, he questioned how
government/Alcohol_Problems/Session4-PDF.txt:Treatment" theme of the National Treatment Plan.36 Alcohol problems
government/Alcohol_Problems/Session4-PDF.txt:The opposite may be the case. Alcohol-related medical problems,
government/Alcohol_Problems/Session4-PDF.txt:Alcohol-related problems occur at lower rates, but in much
government/Alcohol_Problems/Session4-PDF.txt:Alcohol use among emergency department patients is not likely a
government/Alcohol_Problems/Session4-PDF.txt:Regulations (42 C.F.R. Part 2), Confidentiality of Alcohol and Drug
government/Alcohol_Problems/Session4-PDF.txt:treatment. Am J Drug Alcohol Abuse 1996;22:233-46.
government/Alcohol_Problems/Session4-PDF.txt:3. Gentilello LM, Rivara FP, Donovan, DM, et al. Alcohol
government/Alcohol_Problems/Session4-PDF.txt:hospitalized patients. Am J Drug Alcohol Abuse 1997;23:1-13.
government/Alcohol_Problems/Session4-PDF.txt:transition from research into practice. J Stud Alcohol 1994 (12
government/Alcohol_Problems/Session4-PDF.txt:Alcohol Health Res World 1989;15:219-20.
government/Alcohol_Problems/Session4-PDF.txt:20. Selzer ML. The Michigan Alcoholism Screening Test: the
government/Alcohol_Problems/Session4-PDF.txt:21. Krishel S, Richards CF. Alcohol and substance abuse
government/Alcohol_Problems/Session4-PDF.txt:Stud Alcohol 2000;61:912-5.
government/Alcohol_Problems/Session4-PDF.txt:the Alcohol Use Disorders Identification Test (AUDIT). Addiction
government/Alcohol_Problems/Session4-PDF.txt:24. National Institute on Alcohol Abuse and Alcoholism. The
government/Alcohol_Problems/Session4-PDF.txt:Physician's Guide to Helping Patients with Alcohol Problems.
government/Alcohol_Problems/Session4-PDF.txt:28. Soderstrom CA, Dailey JT, Kerns TJ. Alcohol and other
government/Alcohol_Problems/Session4-PDF.txt:30. Babor TF, Higgens-Biddle JC. Alcohol screening and brief
government/Alcohol_Problems/Session4-PDF.txt:Alcohol Problems. Washington (DC): National Academy Press;
government/Alcohol_Problems/Session4-PDF.txt:drinkers in the emergency department. J Stud Alcohol
government/Alcohol_Problems/Session4-PDF.txt:37. Hester RK, Miller WR. Handbook of Alcoholism Treatment
government/Alcohol_Problems/Session4-PDF.txt:39. Gerstein DR, editor. Toward the Prevention of Alcohol
government/Alcohol_Problems/Session4-PDF.txt:hospitalized patients. Am J Drug Alcohol Abuse 1997;23:1-13.
government/Alcohol_Problems/Session4-PDF.txt:49. Gentilello LM, Donovan DM, Dunn CW, and Rivara FP. Alcohol
government/Alcohol_Problems/Session4-PDF.txt:51. New York State Office of Alcoholism and Substance Abuse
government/Alcohol_Problems/Session4-PDF.txt:53. Rostenberg PO, editor. Alcohol and Other Drug Screening of
government/Alcohol_Problems/Session4-PDF.txt:54. Confidentiality of Alcohol and Drug Abuse Patient Records,
government/Alcohol_Problems/Session4-PDF.txt:56. National Institute on Alcohol Abuse and Alcoholism. Twelve
government/Alcohol_Problems/Session4-PDF.txt:on Alcohol Abuse and Alcoholism; 1995. NIH Publication No.
government/Alcohol_Problems/Session4-PDF.txt:intervention-an Advanced Alcohol Problem Identification and
government/Alcohol_Problems/Session4-PDF.txt:Alcohol Screening Day, an NIAAA-sponsored event, is an opportunity
government/Gen_Account_Office/pe1019.txt:Evaluation in Alcohol, Drug Abuse, and Mental Health Programs,
plos/pmed.0020160.txt:        p <0.01). Alcohol use was associated with age and sex only (
```

I found out about all the command-line options of grep mentioned above through a website called 
[geeksforgeeks](https://www.geeksforgeeks.org/grep-command-in-unixlinux/).
