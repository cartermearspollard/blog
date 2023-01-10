---
layout: post
title:  "Language in Byron White's SCOTUS Opinions"
date:   2022-12-19 14:17:12 -0500
categories: research
---
Byron White is notoriously difficult to ideologically categorize. For this reason, 
I thought it would be interesting to look into the language and apply Jonathan Haidt’s
Moral Foundations Theory to see if the language indicated anything about his White’s 
political preferences. The Moral Foundations Theory proposes that there are six moral 
foundations upon which all other values are based: care/harm, fairness/cheating, 
loyalty/betrayal, sanctity/degradation, authority/subversion, and liberty/oppression. 
In his book, _The Righteous Mind_, Haidt proposes that liberals rely primarily on the 
care/harm, fairness/cheating, and loyalty/betrayal foundations while conservatives value 
all six moral foundations. I found that Haidt often applied the theory to language used 
by different political parties, and my inquiry arose out of the question of whether it 
could be applied to such politically ambiguous language as White’s opinions.

I collected 17 opinions, listed in the bibliography, and attempted to analyze their
language based on this mode of questioning. After all files had been downloaded and 
converted to plain text, I began thinking about how I could analyze the data. 
Coincidentally, I had signed up for a short introduction to Python workshop offered 
by the Virginia Tech library, and the very basic skills I had learned during that 
workshop provided me with a place to start using Python for data analysis. I began by 
using the code generously shared with me by another professor in the department, but 
I found that it did not address the types of data I was looking for. I then used a 
Programming Historian tutorial on tf-idf, or Term Frequency-Inverse Document Frequency, 
to find the most used words from each case. In retrospect, I find that my error arises 
from analyzing each document separately rather than as a corpus. The most frequent 
words were very indicative of what each case was about, but they told me little about 
the moral language within the cases. However, at the time, I thought the difficulty 
arose from a lack of appropriate stop words. So, I created my own stop word list 
that was tailored to the language of the law. This helped, but it still did not 
yield the results I was looking for.

At this point, I moved back to Dr. Thompson’s code and used sentiment analysis to see 
if there was anything notable to be found. Again, it did not yield any results I was 
looking for. The language of the law is purposefully neutral, if not stern, and because
of this, I did not find that sentiment analysis yielded useful results. However, using 
her code, I did create a word cloud which enabled me to see that there was interesting 
language within my corpus worth pursuing. Dr. Wiscomb encouraged me to use Word2Vec and 
Stanford’s Named Entity Recognition (NER) program to look more closely at the data from 
a different viewpoint. Although I could not manage to use Word2Vec in Python due to my 
own technical skill limitations, I was able to use Stanza, a Python package developed 
by Stanford’s Named Language Processing Group, to extract all named entities within the 
corpus. NER extracts all persons, locations, and organizations mentioned within a 
document, and I found that this was rather overwhelming as Supreme Court opinions so 
often reference these various entities. I did not find anything of particular note within 
this data, but this can also be attributed to my removal of footnotes when I cleaned 
the data. As I was unable to use Word2Vec in Python, I instead employed topic modeling. 
Although the two are, in retrospect, highly dissimilar, I thought topic models might 
provide something of similar use to the data Word2Vec would have yielded.
	
Using Melanie Walsh’s Introduction to Cultural Analytics & Python topic modeling 
tutorial, I downloaded MALLET and used Little MALLET Wrapper in Python to create my topic 
models. I found that these results were useful, particularly in regards to cases that 
were grouped together in the topic models. I then graphed the probability distributions 
for 15 topics according to which cases were most likely to appear in each topic. Although 
all this data was more than enough to work with, I decided to take one more step and use 
part of speech tagging for my corpus. Again, I used a tutorial from Walsh and applied it 
to my corpus. This yielded by far the most interesting results. I found that White rarely 
used complex language, particularly in his verbs. In this way, my findings were similar 
to “Elements of Judicial Style,” a study of Neil Gorsuch’s opinions conducted by 
Nina Varsava at Stanford.
	
In addition to the text analysis I conducted in Python, I also found that data from the 
Supreme Court Database which catalogs various aspects of each case heard by the Supreme 
Court, including the votes of each justice, the issue area of each case, and the direction 
that each decision moves the Court left or right on the political spectrum. I collected 
the totals for the majority, dissent, and concurring votes of Byron White, 
Thurgood Marshall, Antonin Scalia, Warren Burger, William Rehnquist, Sandra Day O’Connor,
John Harlan II, Potter Stewart, and Earl Warren, all of whom served on the Supreme Court 
with Justice White. This data is particularly interesting in the context it provides for 
the length of White’s tenure on the Court, 31 years, and the proportion of various votes 
in regards to other justices known to be either liberal or conservative.
	
I found that displaying this type of data was difficult to do in an engaging way. In an 
attempt to make it more visually appealing, I used the Programming Historian tutorial on 
data visualization using Bokeh and Pandas in Python to create graphs that I felt 
represented interesting aspects of the data. Bokeh was particularly useful for its hover 
tool which displays additional data not represented in the graph, such as the words or 
total vote counts. Although the graphs are not as sophisticated as they could be, the 
process of learning how to display data in an engaging manner was useful in thinking 
about how I can best display this type of information. Moving forward, I think this 
study could be widened to analyze various justices, as demonstrated in 
“Elements of Judicial Style.” Furthermore, the language of politics in regards to 
political affiliation has become increasingly apparent in its power. The judicial branch 
of government holds enormous amounts of power and has often faded into the background. 
Justices are traditionally non-partisan, but as this is no longer the case, a study of 
their language holds the potential to reveal political affiliations that are otherwise 
difficult to recognize in official opinions. If this study were to be expanded upon, 
a cross referencing of the language used to by politicians and justices could yield 
insight into the rhetoric of politics and the law that would otherwise be obscured. 

---
The totals for each justice whose votes were tallied are represented below. White voted
with the majority roughly 6.62 times as often as he dissented. The only other justice
with a higher proportion of majority votes is Earl Warren who voted with the majority
13.27 times as often as he dissented. The chart also provides insight into tenure length
and the amount of influence held over the court. Well known justices such as Scalia and
O'Connor spent relatively little time on the Court in comparison to White. As a
representation of the power held over a long period of time, this is demonstrative of
how the amount of time spent on the bench translates into power held.

<html lang="en">
  
  <head>
    
      <meta charset="utf-8">
      <title>Bokeh Plot</title>
      
      
        
          
        
        
          
        <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-2.4.2.min.js"></script>
        <script type="text/javascript">
            Bokeh.set_log_level("info");
        </script>
        
      
      
    
  </head>
  
  
  <body>
    
      
        
          
          
            
              <div class="bk-root" id="a511f240-6a95-47e5-af72-bfc9811f5212" data-root-id="2500"></div>
            
          
        
      
      
        <script type="application/json" id="2737">
          {"d1a00364-8210-4e24-b21e-038585abaca1":{"defs":[],"roots":{"references":[{"attributes":{"bottom":{"expr":{"id":"2532"}},"fill_alpha":{"value":0.1},"fill_color":{"value":"#ffffbf"},"hatch_alpha":{"value":0.1},"hatch_color":{"value":"#ffffbf"},"line_alpha":{"value":0.1},"line_color":{"value":"#ffffbf"},"top":{"expr":{"id":"2533"}},"width":{"value":0.4},"x":{"field":"Justice"}},"id":"2557","type":"VBar"},{"attributes":{},"id":"2549","type":"AllLabels"},{"attributes":{"coordinates":null,"group":null,"items":[{"id":"2554"},{"id":"2572"},{"id":"2590"}]},"id":"2553","type":"Legend"},{"attributes":{"bottom_units":"screen","coordinates":null,"fill_alpha":0.5,"fill_color":"lightgrey","group":null,"left_units":"screen","level":"overlay","line_alpha":1.0,"line_color":"black","line_dash":[4,4],"line_width":2,"right_units":"screen","syncable":false,"top_units":"screen"},"id":"2522","type":"BoxAnnotation"},{"attributes":{"fields":["Majority"]},"id":"2531","type":"Stack"},{"attributes":{},"id":"2521","type":"HelpTool"},{"attributes":{"bottom":{"expr":{"id":"2534"}},"fill_color":{"value":"#fc8d59"},"hatch_color":{"value":"#fc8d59"},"line_color":{"value":"#fc8d59"},"top":{"expr":{"id":"2535"}},"width":{"value":0.4},"x":{"field":"Justice"}},"id":"2574","type":"VBar"},{"attributes":{"fields":["Majority","Dissent"]},"id":"2534","type":"Stack"},{"attributes":{"axis_label":"Justice","coordinates":null,"formatter":{"id":"2548"},"group":null,"major_label_policy":{"id":"2549"},"ticker":{"id":"2510"}},"id":"2509","type":"CategoricalAxis"},{"attributes":{"bottom":{"expr":{"id":"2532"}},"fill_color":{"value":"#ffffbf"},"hatch_color":{"value":"#ffffbf"},"line_color":{"value":"#ffffbf"},"top":{"expr":{"id":"2533"}},"width":{"value":0.4},"x":{"field":"Justice"}},"id":"2556","type":"VBar"},{"attributes":{"coordinates":null,"data_source":{"id":"2499"},"glyph":{"id":"2574"},"group":null,"hover_glyph":null,"muted_glyph":{"id":"2576"},"name":"Regular_Concurrence","nonselection_glyph":{"id":"2575"},"view":{"id":"2578"}},"id":"2577","type":"GlyphRenderer"},{"attributes":{},"id":"2545","type":"BasicTickFormatter"},{"attributes":{"coordinates":null,"data_source":{"id":"2499"},"glyph":{"id":"2556"},"group":null,"hover_glyph":null,"muted_glyph":{"id":"2558"},"name":"Dissent","nonselection_glyph":{"id":"2557"},"view":{"id":"2560"}},"id":"2559","type":"GlyphRenderer"},{"attributes":{"below":[{"id":"2509"}],"center":[{"id":"2511"},{"id":"2515"},{"id":"2553"}],"left":[{"id":"2512"}],"renderers":[{"id":"2540"},{"id":"2559"},{"id":"2577"}],"title":{"id":"2542"},"toolbar":{"id":"2523"},"x_range":{"id":"2501"},"x_scale":{"id":"2505"},"y_range":{"id":"2503"},"y_scale":{"id":"2507"}},"id":"2500","subtype":"Figure","type":"Plot"},{"attributes":{},"id":"2505","type":"CategoricalScale"},{"attributes":{},"id":"2550","type":"UnionRenderers"},{"attributes":{},"id":"2546","type":"AllLabels"},{"attributes":{"tools":[{"id":"2516"},{"id":"2517"},{"id":"2518"},{"id":"2519"},{"id":"2520"},{"id":"2521"},{"id":"2592"}]},"id":"2523","type":"Toolbar"},{"attributes":{"axis_label":"Total Number of Votes","coordinates":null,"formatter":{"id":"2545"},"group":null,"major_label_policy":{"id":"2546"},"ticker":{"id":"2513"}},"id":"2512","type":"LinearAxis"},{"attributes":{"bottom":{"expr":{"id":"2534"}},"fill_alpha":{"value":0.1},"fill_color":{"value":"#fc8d59"},"hatch_alpha":{"value":0.1},"hatch_color":{"value":"#fc8d59"},"line_alpha":{"value":0.1},"line_color":{"value":"#fc8d59"},"top":{"expr":{"id":"2535"}},"width":{"value":0.4},"x":{"field":"Justice"}},"id":"2575","type":"VBar"},{"attributes":{"callback":null,"mode":"vline","tooltips":[["Totals","@Majority Majority / @Dissent Dissent / @Regular_Concurrence Concurrence"]]},"id":"2592","type":"HoverTool"},{"attributes":{},"id":"2551","type":"Selection"},{"attributes":{"bottom":{"expr":{"id":"2534"}},"fill_alpha":{"value":0.2},"fill_color":{"value":"#fc8d59"},"hatch_alpha":{"value":0.2},"hatch_color":{"value":"#fc8d59"},"line_alpha":{"value":0.2},"line_color":{"value":"#fc8d59"},"top":{"expr":{"id":"2535"}},"width":{"value":0.4},"x":{"field":"Justice"}},"id":"2576","type":"VBar"},{"attributes":{"bottom":{"expr":{"id":"2530"}},"fill_color":{"value":"#99d594"},"hatch_color":{"value":"#99d594"},"line_color":{"value":"#99d594"},"top":{"expr":{"id":"2531"}},"width":{"value":0.4},"x":{"field":"Justice"}},"id":"2537","type":"VBar"},{"attributes":{},"id":"2510","type":"CategoricalTicker"},{"attributes":{"data":{"Dissent":[588,76,401,495,253,358,608,137,968],"Justice":["White","Ewarren","JHarlan","PStewart","SDOConnor","WEBurger","WHRehnquist","Ascalia","TMarshall"],"Majority":[3893,1009,752,2293,1342,2106,2520,665,2337],"Regular_Concurrence":[114,14,76,88,87,123,74,49,100]},"selected":{"id":"2551"},"selection_policy":{"id":"2550"}},"id":"2499","type":"ColumnDataSource"},{"attributes":{"fields":[]},"id":"2530","type":"Stack"},{"attributes":{"source":{"id":"2499"}},"id":"2578","type":"CDSView"},{"attributes":{"bottom":{"expr":{"id":"2532"}},"fill_alpha":{"value":0.2},"fill_color":{"value":"#ffffbf"},"hatch_alpha":{"value":0.2},"hatch_color":{"value":"#ffffbf"},"line_alpha":{"value":0.2},"line_color":{"value":"#ffffbf"},"top":{"expr":{"id":"2533"}},"width":{"value":0.4},"x":{"field":"Justice"}},"id":"2558","type":"VBar"},{"attributes":{"label":{"value":"Regular Concurrence"},"renderers":[{"id":"2577"}]},"id":"2590","type":"LegendItem"},{"attributes":{"fields":["Majority","Dissent","Regular_Concurrence"]},"id":"2535","type":"Stack"},{"attributes":{"source":{"id":"2499"}},"id":"2560","type":"CDSView"},{"attributes":{},"id":"2507","type":"LinearScale"},{"attributes":{"coordinates":null,"data_source":{"id":"2499"},"glyph":{"id":"2537"},"group":null,"hover_glyph":null,"muted_glyph":{"id":"2539"},"name":"Majority","nonselection_glyph":{"id":"2538"},"view":{"id":"2541"}},"id":"2540","type":"GlyphRenderer"},{"attributes":{"fields":["Majority"]},"id":"2532","type":"Stack"},{"attributes":{},"id":"2516","type":"PanTool"},{"attributes":{"fields":["Majority","Dissent"]},"id":"2533","type":"Stack"},{"attributes":{},"id":"2520","type":"ResetTool"},{"attributes":{"axis":{"id":"2509"},"coordinates":null,"grid_line_color":null,"group":null,"ticker":null},"id":"2511","type":"Grid"},{"attributes":{"overlay":{"id":"2522"}},"id":"2518","type":"BoxZoomTool"},{"attributes":{"bottom":{"expr":{"id":"2530"}},"fill_alpha":{"value":0.2},"fill_color":{"value":"#99d594"},"hatch_alpha":{"value":0.2},"hatch_color":{"value":"#99d594"},"line_alpha":{"value":0.2},"line_color":{"value":"#99d594"},"top":{"expr":{"id":"2531"}},"width":{"value":0.4},"x":{"field":"Justice"}},"id":"2539","type":"VBar"},{"attributes":{},"id":"2517","type":"WheelZoomTool"},{"attributes":{"label":{"value":"Dissent"},"renderers":[{"id":"2559"}]},"id":"2572","type":"LegendItem"},{"attributes":{"label":{"value":"Majority"},"renderers":[{"id":"2540"}]},"id":"2554","type":"LegendItem"},{"attributes":{},"id":"2548","type":"CategoricalTickFormatter"},{"attributes":{"bottom":{"expr":{"id":"2530"}},"fill_alpha":{"value":0.1},"fill_color":{"value":"#99d594"},"hatch_alpha":{"value":0.1},"hatch_color":{"value":"#99d594"},"line_alpha":{"value":0.1},"line_color":{"value":"#99d594"},"top":{"expr":{"id":"2531"}},"width":{"value":0.4},"x":{"field":"Justice"}},"id":"2538","type":"VBar"},{"attributes":{},"id":"2513","type":"BasicTicker"},{"attributes":{"factors":["White","Ewarren","JHarlan","PStewart","SDOConnor","WEBurger","WHRehnquist","Ascalia","TMarshall"]},"id":"2501","type":"FactorRange"},{"attributes":{"axis":{"id":"2512"},"coordinates":null,"dimension":1,"group":null,"ticker":null},"id":"2515","type":"Grid"},{"attributes":{"coordinates":null,"group":null,"text":"Type of Vote Sorted by Justice"},"id":"2542","type":"Title"},{"attributes":{},"id":"2503","type":"DataRange1d"},{"attributes":{"source":{"id":"2499"}},"id":"2541","type":"CDSView"},{"attributes":{},"id":"2519","type":"SaveTool"}],"root_ids":["2500"]},"title":"Bokeh Application","version":"2.4.2"}}
        </script>
        <script type="text/javascript">
          (function() {
            const fn = function() {
              Bokeh.safely(function() {
                (function(root) {
                  function embed_document(root) {
                    
                  const docs_json = document.getElementById('2737').textContent;
                  const render_items = [{"docid":"d1a00364-8210-4e24-b21e-038585abaca1","root_ids":["2500"],"roots":{"2500":"a511f240-6a95-47e5-af72-bfc9811f5212"}}];
                  root.Bokeh.embed.embed_items(docs_json, render_items);
                
                  }
                  if (root.Bokeh !== undefined) {
                    embed_document(root);
                  } else {
                    let attempts = 0;
                    const timer = setInterval(function(root) {
                      if (root.Bokeh !== undefined) {
                        clearInterval(timer);
                        embed_document(root);
                      } else {
                        attempts++;
                        if (attempts > 100) {
                          clearInterval(timer);
                          console.log("Bokeh: ERROR: Unable to run BokehJS code because BokehJS library is missing");
                        }
                      }
                    }, 10, root)
                  }
                })(window);
              });
            };
            if (document.readyState != "loading") fn();
            else document.addEventListener("DOMContentLoaded", fn);
          })();
        </script>
    
  </body>
  
</html>
---

The topics included in the visualization are as follows:
0.	school, board, immunity, girls, good, respondents, regulation, meeting, faith,
public, liability, student, petitioners, intoxicating, action, damages, members,
waller, punch, district
1.	districts', plan, population, state, political, district, reapportionment, board,
equality, house, variations, legislative, among, equal, census, deviation, vote, reynolds,
apportionment, senate
2.	right, sodomy, stanley, obscenity, respondent, roth, home, georgia, homosexual,
obscene, fundamental, rights, statute, privacy, conduct, material, reidel, first, laws,
private
3.	waiver, columbia, enforcement, washington, jackson, sixth, inbau, values, hara,
vignera, appointed, lie, reports, extension, apart, prove, probation, pleas, excluding,
mapp
4.	federal, questions, station, written, administration, legal, reported, practices,
laid, recent, render, necessarily, data, restrictions, absence, read, thing, ability,
refusal, completely
5.	police, interrogation, confession, see, confessions, counsel, states, new, accused,
privilege, united, rev, court, fifth, rules, defendant, suspect, rule, today, evidence
6.	editorial, publication, liability, evidence, first, defendant, process, inquiry,
defamation, false, plaintiff, new, case, reckless, york, proof, press, times, plaintiffs,
knowing
7.	grand, jury, information, press, news, privilege, first, sources, petitioner,
reporter, criminal, reporters, newsmen, united, amendment, caldwell, testify, crime,
confidential, appear
8.	life, constitutionally, people, convenience, health, georgia, abortion, mother, fetus,
existence, likewise, statute, page, mothers, family, men, fall, values, children, language
9.	public, first, interest, new, political, speech, rules, order, press, committee,
could, importance, app, views, provisions, making, also, television, report, specific
10.	radio, fcc, broadcasting, doctrine, broadcast, regulations, fairness, time,
commission, frequencies, government, license, congress, station, act, personal,
communications, attack, news, issues
11.	amendment, may, states, would, one, must, united, without, right, upon, even, fact,
see, issue, general, view, cases, two, question, protection
12.	criminal, though, examination, supreme, code, american, cited, conviction, described,
justice, short, security, inquiry, crime, open, city, illinois, appears, still, stewart
13.	court, state, law cas, also, cases, whether, supra, however, district, evidence,
opinion, courts, constitution, federal, constitutional, time, attorney, made, process
14.	school, schools, books, state, general, religion, religious, education, secular, law,
appellants, textbooks, students, public, york, attorney, children, parochial, new, free
15.	texas, board, regents, judge, three, statewide, rules, jurisdiction, statute,
education, attorneys, local, appellant, appeal, convened, university, higher, 
inconsistent, western, system

Upon inspection, it becomes clear that in topic modeling, I did not use lemmatization or
the custom stop word list I created. Moving forward, these would necessarily be applied
in order to create more diverse and representative topic models. However, in their current
state they still yield interesting information.

<html lang="en">
  
  <head>
    
      <meta charset="utf-8">
      <title>Bokeh Plot</title>
      
      
        
          
        
        
          
        <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-2.4.2.min.js"></script>
        <script type="text/javascript">
            Bokeh.set_log_level("info");
        </script>
        
      
      
    
  </head>
  
  
  <body>
    
      
        
          
          
            
              <div class="bk-root" id="20bf6718-72d6-472e-8e68-7925a04eadd5" data-root-id="1003"></div>
            
          
        
      
      
        <script type="application/json" id="1187">
          {"22a22825-0b40-4bba-b51e-06a1c4266ddf":{"defs":[],"roots":{"references":[{"attributes":{"axis":{"id":"1016"},"coordinates":null,"dimension":1,"group":null,"ticker":null},"id":"1019","type":"Grid"},{"attributes":{},"id":"1004","type":"DataRange1d"},{"attributes":{"callback":null,"tooltips":[["Case Citation","@{Case Title}"]]},"id":"1042","type":"HoverTool"},{"attributes":{"axis":{"id":"1012"},"coordinates":null,"group":null,"ticker":null},"id":"1015","type":"Grid"},{"attributes":{"below":[{"id":"1012"}],"center":[{"id":"1015"},{"id":"1019"}],"left":[{"id":"1016"}],"renderers":[{"id":"1038"}],"title":{"id":"1044"},"toolbar":{"id":"1027"},"x_range":{"id":"1004"},"x_scale":{"id":"1008"},"y_range":{"id":"1006"},"y_scale":{"id":"1010"}},"id":"1003","subtype":"Figure","type":"Plot"},{"attributes":{},"id":"1008","type":"LinearScale"},{"attributes":{},"id":"1047","type":"BasicTickFormatter"},{"attributes":{},"id":"1013","type":"BasicTicker"},{"attributes":{},"id":"1010","type":"LinearScale"},{"attributes":{},"id":"1048","type":"AllLabels"},{"attributes":{},"id":"1025","type":"HelpTool"},{"attributes":{},"id":"1023","type":"SaveTool"},{"attributes":{},"id":"1050","type":"BasicTickFormatter"},{"attributes":{},"id":"1051","type":"AllLabels"},{"attributes":{"overlay":{"id":"1026"}},"id":"1022","type":"BoxZoomTool"},{"attributes":{},"id":"1020","type":"PanTool"},{"attributes":{"tools":[{"id":"1020"},{"id":"1021"},{"id":"1022"},{"id":"1023"},{"id":"1024"},{"id":"1025"},{"id":"1042"}]},"id":"1027","type":"Toolbar"},{"attributes":{},"id":"1017","type":"BasicTicker"},{"attributes":{},"id":"1006","type":"DataRange1d"},{"attributes":{"fill_alpha":{"value":0.1},"fill_color":{"value":"blue"},"hatch_alpha":{"value":0.1},"hatch_color":{"value":"blue"},"line_alpha":{"value":0.1},"line_color":{"value":"blue"},"size":{"value":3},"x":{"field":"Topic Number"},"y":{"field":"Value"}},"id":"1036","type":"Circle"},{"attributes":{"coordinates":null,"group":null},"id":"1044","type":"Title"},{"attributes":{"coordinates":null,"data_source":{"id":"1002"},"glyph":{"id":"1035"},"group":null,"hover_glyph":null,"muted_glyph":{"id":"1037"},"nonselection_glyph":{"id":"1036"},"view":{"id":"1039"}},"id":"1038","type":"GlyphRenderer"},{"attributes":{},"id":"1024","type":"ResetTool"},{"attributes":{"coordinates":null,"formatter":{"id":"1047"},"group":null,"major_label_policy":{"id":"1048"},"ticker":{"id":"1017"}},"id":"1016","type":"LinearAxis"},{"attributes":{"source":{"id":"1002"}},"id":"1039","type":"CDSView"},{"attributes":{},"id":"1052","type":"UnionRenderers"},{"attributes":{"fill_color":{"value":"blue"},"hatch_color":{"value":"blue"},"line_color":{"value":"blue"},"size":{"value":3},"x":{"field":"Topic Number"},"y":{"field":"Value"}},"id":"1035","type":"Circle"},{"attributes":{"data":{"Case Title":["420 US 308","404 US 541","402 US 351","404 US 541","379 US 184","384 US 436","395 US 3","478 US 186","402 US 351","402 US 351","408 US 665","404 US 541","478 US 186","404 US 541","478 US 186","387 US 523","436 US 547","412 US 735","410 US 113","387 US 523","461 US 138","408 US 665","404 US 541","461 US 138","380 US 202","395 US 3","404 US 541","384 US 436","395 US 3","379 US 184","410 US 113","408 US 665","408 US 665","384 US 436","408 US 665","478 US 186","408 US 665","461 US 138","412 US 735","478 US 186","410 US 113","402 US 351","478 US 186","410 US 113","380 US 202","392 US 236","404 US 541","404 US 541","384 US 436","410 US 113","478 US 186","478 US 186","412 US 735","404 US 541","410 US 113","384 US 436","395 US 3","404 US 541","379 US 184","410 US 113","436 US 547","402 US 351","441 US 153","478 US 186","461 US 138","402 US 351","408 US 665","420 US 308","438 US 478","461 US 138","441 US 153","420 US 308","438 US 478","410 US 113","441 US 153","438 US 478","387 US 523","384 US 436","436 US 547","402 US 351"],"Topic Number":[0,5,8,3,11,3,9,2,10,14,7,13,8,10,1,12,11,11,3,11,14,8,9,0,11,10,1,0,4,12,13,4,5,12,9,15,2,4,15,13,7,1,10,1,12,14,14,15,5,8,12,14,1,0,5,4,8,7,2,2,6,5,6,3,15,2,6,4,6,9,9,6,0,10,7,13,15,13,7,3],"Value":{"__ndarray__":"p3nHKTqS2z8tQxzr4jYaP1OWIY51cas/AAAAAAAAAABHcvkP6bfHPwmKH2PuWrI/NxrAWyBByT+u2F92Tx7aPwAAAAAAAAAALUMc6+I2Wj9GlPYGX5jcP9NNYhBYOcw/KVyPwvUonD8AAAAAAAAAAAAAAAAAAAAAY+5aQj7omT8wKqkT0ETIP9v5fmq8dMs/AAAAAAAAAAAldQKaCBvOP5LLf0i/fX0/x7q4jQbwhj/1udqK/WWnP+CcEaW9wYc/uY0G8BZIyD82zTtO0ZHcPwAAAAAAAAAA+n5qvHSTaD/+ZffkYaGmP7wFEhQ/xqw/YVRSJ6CJyD9EaW/whcmUPxkEVg4tso0/Vg4tsp3vtz/ByqFFtvOtPzj4wmSqYJQ/LUMc6+I2Oj/sUbgeheuRP7gehetRuI4/F9nO91PjzT8tQxzr4jYaPwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAO0NvjCZKqg/UiegibDh4z/HuriNBvB2PyEf9GxWfeI/0NVW7C+70z+jkjoBTYTdPzLmriXkg64/MuauJeSDnj/u68A5I0rjP8WPMXctIV8/RiV1ApoIaz/pSC7/If2mP3ZxGw3gLYA/LUMc6+I2Gj9GJXUCmghrPy1DHOviNio/3nGKjuTyjz8730+Nl25yP/kP6bevA+E/AAAAAAAAAAA5tMh2vp+aPwWjkjoBTdw/gLdAguLHiD/gnBGlvcGHP7pJDAIrh4Y/vsEXJlMFsz/RItv5fmqsP15LyAc9m5U/SFD8GHPXgj8AAAAAAAAAAPp+arx0k4g/7nw/NV66yT/UK2UZ4lh3P0oMAiuHFsk/MCqpE9BEmD8AAAAAAAAAAA==","dtype":"float64","order":"little","shape":[80]},"index":[0,29,41,17,59,15,45,11,53,74,35,66,42,52,9,64,58,56,16,55,72,43,49,1,57,50,7,4,21,62,69,22,26,60,47,77,13,23,78,65,38,8,54,6,63,70,73,75,25,40,61,71,5,3,28,20,44,39,12,14,32,27,30,19,76,10,33,24,34,46,48,31,2,51,37,67,79,68,36,18]},"selected":{"id":"1053"},"selection_policy":{"id":"1052"}},"id":"1002","type":"ColumnDataSource"},{"attributes":{"bottom_units":"screen","coordinates":null,"fill_alpha":0.5,"fill_color":"lightgrey","group":null,"left_units":"screen","level":"overlay","line_alpha":1.0,"line_color":"black","line_dash":[4,4],"line_width":2,"right_units":"screen","syncable":false,"top_units":"screen"},"id":"1026","type":"BoxAnnotation"},{"attributes":{},"id":"1053","type":"Selection"},{"attributes":{"coordinates":null,"formatter":{"id":"1050"},"group":null,"major_label_policy":{"id":"1051"},"ticker":{"id":"1013"}},"id":"1012","type":"LinearAxis"},{"attributes":{"fill_alpha":{"value":0.2},"fill_color":{"value":"blue"},"hatch_alpha":{"value":0.2},"hatch_color":{"value":"blue"},"line_alpha":{"value":0.2},"line_color":{"value":"blue"},"size":{"value":3},"x":{"field":"Topic Number"},"y":{"field":"Value"}},"id":"1037","type":"Circle"},{"attributes":{},"id":"1021","type":"WheelZoomTool"}],"root_ids":["1003"]},"title":"Bokeh Application","version":"2.4.2"}}
        </script>
        <script type="text/javascript">
          (function() {
            const fn = function() {
              Bokeh.safely(function() {
                (function(root) {
                  function embed_document(root) {
                    
                  const docs_json = document.getElementById('1187').textContent;
                  const render_items = [{"docid":"22a22825-0b40-4bba-b51e-06a1c4266ddf","root_ids":["1003"],"roots":{"1003":"20bf6718-72d6-472e-8e68-7925a04eadd5"}}];
                  root.Bokeh.embed.embed_items(docs_json, render_items);
                
                  }
                  if (root.Bokeh !== undefined) {
                    embed_document(root);
                  } else {
                    let attempts = 0;
                    const timer = setInterval(function(root) {
                      if (root.Bokeh !== undefined) {
                        clearInterval(timer);
                        embed_document(root);
                      } else {
                        attempts++;
                        if (attempts > 100) {
                          clearInterval(timer);
                          console.log("Bokeh: ERROR: Unable to run BokehJS code because BokehJS library is missing");
                        }
                      }
                    }, 10, root)
                  }
                })(window);
              });
            };
            if (document.readyState != "loading") fn();
            else document.addEventListener("DOMContentLoaded", fn);
          })();
        </script>
    
  </body>
  
</html>



White's verb choice is represented on the scatter plot below from the most used verb, 
"see" to the 150th verb, "expressed." Although some might claim that the top few words
are not worth expressing in data, I would contest the opposite. The visual representation
makes clear the difference in usage between verbs such as "sought" (30 times) and "see"
(roughly 127 times). The language White uses in his opinions is not relatively simple,
which I would contest adds to the argument that his familial background and conservative 
personal values influenced, at the very least, his rhetoric.

<html lang="en">
  
  <head>
    
      <meta charset="utf-8">
      <title>Bokeh Plot</title>
      
      
        
          
        
        
          
        <script type="text/javascript" src="https://cdn.bokeh.org/bokeh/release/bokeh-2.4.2.min.js"></script>
        <script type="text/javascript">
            Bokeh.set_log_level("info");
        </script>
        
      
      
    
  </head>
  
  
  <body>
    
      
        
          
          
            
              <div class="bk-root" id="b17b56ce-d95a-428f-a966-da7da4b9e2a5" data-root-id="1244"></div>
            
          
        
      
      
        <script type="application/json" id="1429">
          {"bb734f9f-f4a1-44eb-a2da-2da5bf1f23a0":{"defs":[],"roots":{"references":[{"attributes":{"data":{"Count":[129,94,94,91,86,61,59,58,51,51,50,49,48,43,42,41,41,38,37,37,37,36,35,35,34,34,33,33,33,32,31,31,30,30,28,28,28,27,27,26,26,26,26,25,24,24,24,24,24,24,23,23,22,22,22,22,22,22,21,21,21,21,21,21,21,20,20,20,20,20,19,19,19,19,19,19,18,18,18,18,18,18,18,18,18,18,18,18,17,17,17,17,17,17,16,16,16,16,16,16,16,16,15,15,15,15,15,15,15,15,15,15,14,14,14,14,14,14,14,14,14,14,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,13,12,12,12],"Rank":{"__ndarray__":"AAAAAAAA8D8AAAAAAAAAQAAAAAAAAAhAAAAAAAAAEEAAAAAAAAAUQAAAAAAAABhAAAAAAAAAHEAAAAAAAAAgQAAAAAAAACJAAAAAAAAAJEAAAAAAAAAmQAAAAAAAAChAAAAAAAAAKkAAAAAAAAAsQAAAAAAAAC5AAAAAAAAAMEAAAAAAAAAxQAAAAAAAADJAAAAAAAAAM0AAAAAAAAA0QAAAAAAAADVAAAAAAAAANkAAAAAAAAA3QAAAAAAAADhAAAAAAAAAOUAAAAAAAAA6QAAAAAAAADtAAAAAAAAAPEAAAAAAAAA9QAAAAAAAAD5AAAAAAAAAP0AAAAAAAABAQAAAAAAAgEBAAAAAAAAAQUAAAAAAAIBBQAAAAAAAAEJAAAAAAACAQkAAAAAAAABDQAAAAAAAgENAAAAAAAAAREAAAAAAAIBEQAAAAAAAAEVAAAAAAACARUAAAAAAAABGQAAAAAAAgEZAAAAAAAAAR0AAAAAAAIBHQAAAAAAAAEhAAAAAAACASEAAAAAAAABJQAAAAAAAgElAAAAAAAAASkAAAAAAAIBKQAAAAAAAAEtAAAAAAACAS0AAAAAAAABMQAAAAAAAgExAAAAAAAAATUAAAAAAAIBNQAAAAAAAAE5AAAAAAACATkAAAAAAAABPQAAAAAAAgE9AAAAAAAAAUEAAAAAAAEBQQAAAAAAAgFBAAAAAAADAUEAAAAAAAABRQAAAAAAAQFFAAAAAAACAUUAAAAAAAMBRQAAAAAAAAFJAAAAAAABAUkAAAAAAAIBSQAAAAAAAwFJAAAAAAAAAU0AAAAAAAEBTQAAAAAAAgFNAAAAAAADAU0AAAAAAAABUQAAAAAAAQFRAAAAAAACAVEAAAAAAAMBUQAAAAAAAAFVAAAAAAABAVUAAAAAAAIBVQAAAAAAAwFVAAAAAAAAAVkAAAAAAAEBWQAAAAAAAgFZAAAAAAADAVkAAAAAAAABXQAAAAAAAQFdAAAAAAACAV0AAAAAAAMBXQAAAAAAAAFhAAAAAAABAWEAAAAAAAIBYQAAAAAAAwFhAAAAAAAAAWUAAAAAAAEBZQAAAAAAAgFlAAAAAAADAWUAAAAAAAABaQAAAAAAAQFpAAAAAAACAWkAAAAAAAMBaQAAAAAAAAFtAAAAAAABAW0AAAAAAAIBbQAAAAAAAwFtAAAAAAAAAXEAAAAAAAEBcQAAAAAAAgFxAAAAAAADAXEAAAAAAAABdQAAAAAAAQF1AAAAAAACAXUAAAAAAAMBdQAAAAAAAAF5AAAAAAABAXkAAAAAAAIBeQAAAAAAAwF5AAAAAAAAAX0AAAAAAAEBfQAAAAAAAgF9AAAAAAADAX0AAAAAAAABgQAAAAAAAIGBAAAAAAABAYEAAAAAAAGBgQAAAAAAAgGBAAAAAAACgYEAAAAAAAMBgQAAAAAAA4GBAAAAAAAAAYUAAAAAAACBhQAAAAAAAQGFAAAAAAABgYUAAAAAAAIBhQAAAAAAAoGFAAAAAAADAYUAAAAAAAOBhQAAAAAAAAGJAAAAAAAAgYkAAAAAAAEBiQAAAAAAAYGJAAAAAAACAYkAAAAAAAKBiQAAAAAAAwGJA","dtype":"float64","order":"little","shape":[150]},"Verb":["See","held","made","is","have","has","involved","make","said","see","had","accused","required","given","believe","found","based","require","protected","denied","entitled","say","applied","appear","hold","requiring","presented","do","committed","argued","recognized","served","think","sought","requires","stated","issued","was","making","taken","authorized","searched","compelled","concluded","including","considered","used","are","give","search","concerning","answer","prove","imposed","prevent","alleged","justify","issue","filed","agree","claimed","protect","makes","testify","show","brought","provided","seek","noted","permit","granted","construed","announced","provide","obtain","suggested","charged","having","deemed","thought","consider","published","refused","established","obtained","failed","determining","remain","decided","reversed","drawn","sued","serve","cited","violated","appears","rejected","struck","known","suspected","involving","exceeding","affirmed","described","reach","ordered","publish","intended","seized","put","quash","refuse","delivered","urged","defined","justified","shown","existing","assert","does","provides","dissenting","asserted","supported","done","involves","read","offered","support","declared","concurring","relating","suggest","told","observed","conclude","directed","perform","relied","broadcast","knowing","adopted","know","acting","took","use","deal","present","placed","expressed"],"index":[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41,42,43,44,45,46,47,48,49,50,51,52,53,54,55,56,57,58,59,60,61,62,63,64,65,66,67,68,69,70,71,72,73,74,75,76,77,78,79,80,81,82,83,84,85,86,87,88,89,90,91,92,93,94,95,96,97,98,99,100,101,102,103,104,105,106,107,108,109,110,111,112,113,114,115,116,117,118,119,120,121,122,123,124,125,126,127,128,129,130,131,132,133,134,135,136,137,138,139,140,141,142,143,144,145,146,147,148,149]},"selected":{"id":"1295"},"selection_policy":{"id":"1294"}},"id":"1243","type":"ColumnDataSource"},{"attributes":{"fill_alpha":{"value":0.2},"fill_color":{"value":"pink"},"hatch_alpha":{"value":0.2},"hatch_color":{"value":"pink"},"line_alpha":{"value":0.2},"line_color":{"value":"pink"},"x":{"field":"Rank"},"y":{"field":"Count"}},"id":"1278","type":"Circle"},{"attributes":{"axis_label":"Verb Rank","coordinates":null,"formatter":{"id":"1292"},"group":null,"major_label_policy":{"id":"1293"},"ticker":{"id":"1254"}},"id":"1253","type":"LinearAxis"},{"attributes":{},"id":"1265","type":"ResetTool"},{"attributes":{"coordinates":null,"data_source":{"id":"1243"},"glyph":{"id":"1276"},"group":null,"hover_glyph":null,"muted_glyph":{"id":"1278"},"nonselection_glyph":{"id":"1277"},"view":{"id":"1280"}},"id":"1279","type":"GlyphRenderer"},{"attributes":{},"id":"1289","type":"BasicTickFormatter"},{"attributes":{"bottom_units":"screen","coordinates":null,"fill_alpha":0.5,"fill_color":"lightgrey","group":null,"left_units":"screen","level":"overlay","line_alpha":1.0,"line_color":"black","line_dash":[4,4],"line_width":2,"right_units":"screen","syncable":false,"top_units":"screen"},"id":"1267","type":"BoxAnnotation"},{"attributes":{"source":{"id":"1243"}},"id":"1280","type":"CDSView"},{"attributes":{"overlay":{"id":"1267"}},"id":"1263","type":"BoxZoomTool"},{"attributes":{},"id":"1290","type":"AllLabels"},{"attributes":{},"id":"1249","type":"LinearScale"},{"attributes":{},"id":"1266","type":"HelpTool"},{"attributes":{},"id":"1292","type":"BasicTickFormatter"},{"attributes":{"below":[{"id":"1253"}],"center":[{"id":"1256"},{"id":"1260"}],"left":[{"id":"1257"}],"renderers":[{"id":"1279"}],"title":{"id":"1283"},"toolbar":{"id":"1268"},"x_range":{"id":"1245"},"x_scale":{"id":"1249"},"y_range":{"id":"1247"},"y_scale":{"id":"1251"}},"id":"1244","subtype":"Figure","type":"Plot"},{"attributes":{},"id":"1293","type":"AllLabels"},{"attributes":{"fill_alpha":{"value":0.1},"fill_color":{"value":"pink"},"hatch_alpha":{"value":0.1},"hatch_color":{"value":"pink"},"line_alpha":{"value":0.1},"line_color":{"value":"pink"},"x":{"field":"Rank"},"y":{"field":"Count"}},"id":"1277","type":"Circle"},{"attributes":{},"id":"1264","type":"SaveTool"},{"attributes":{},"id":"1247","type":"DataRange1d"},{"attributes":{},"id":"1258","type":"BasicTicker"},{"attributes":{"fill_color":{"value":"pink"},"hatch_color":{"value":"pink"},"line_color":{"value":"pink"},"x":{"field":"Rank"},"y":{"field":"Count"}},"id":"1276","type":"Circle"},{"attributes":{},"id":"1261","type":"PanTool"},{"attributes":{},"id":"1251","type":"LinearScale"},{"attributes":{},"id":"1254","type":"BasicTicker"},{"attributes":{"tools":[{"id":"1261"},{"id":"1262"},{"id":"1263"},{"id":"1264"},{"id":"1265"},{"id":"1266"},{"id":"1284"}]},"id":"1268","type":"Toolbar"},{"attributes":{},"id":"1262","type":"WheelZoomTool"},{"attributes":{},"id":"1294","type":"UnionRenderers"},{"attributes":{"axis":{"id":"1257"},"coordinates":null,"dimension":1,"group":null,"ticker":null},"id":"1260","type":"Grid"},{"attributes":{"axis":{"id":"1253"},"coordinates":null,"group":null,"ticker":null},"id":"1256","type":"Grid"},{"attributes":{},"id":"1295","type":"Selection"},{"attributes":{},"id":"1245","type":"DataRange1d"},{"attributes":{"axis_label":"Total Times Used","coordinates":null,"formatter":{"id":"1289"},"group":null,"major_label_policy":{"id":"1290"},"ticker":{"id":"1258"}},"id":"1257","type":"LinearAxis"},{"attributes":{"callback":null,"tooltips":[["Verb","@Verb"]]},"id":"1284","type":"HoverTool"},{"attributes":{"coordinates":null,"group":null,"text":"White 150 Most Common Verbs"},"id":"1283","type":"Title"}],"root_ids":["1244"]},"title":"Bokeh Application","version":"2.4.2"}}
        </script>
        <script type="text/javascript">
          (function() {
            const fn = function() {
              Bokeh.safely(function() {
                (function(root) {
                  function embed_document(root) {
                    
                  const docs_json = document.getElementById('1429').textContent;
                  const render_items = [{"docid":"bb734f9f-f4a1-44eb-a2da-2da5bf1f23a0","root_ids":["1244"],"roots":{"1244":"b17b56ce-d95a-428f-a966-da7da4b9e2a5"}}];
                  root.Bokeh.embed.embed_items(docs_json, render_items);
                
                  }
                  if (root.Bokeh !== undefined) {
                    embed_document(root);
                  } else {
                    let attempts = 0;
                    const timer = setInterval(function(root) {
                      if (root.Bokeh !== undefined) {
                        clearInterval(timer);
                        embed_document(root);
                      } else {
                        attempts++;
                        if (attempts > 100) {
                          clearInterval(timer);
                          console.log("Bokeh: ERROR: Unable to run BokehJS code because BokehJS library is missing");
                        }
                      }
                    }, 10, root)
                  }
                })(window);
              });
            };
            if (document.readyState != "loading") fn();
            else document.addEventListener("DOMContentLoaded", fn);
          })();
        </script>
    
  </body>
  
</html>