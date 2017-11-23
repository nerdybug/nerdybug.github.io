---
layout: post
title:      "Mistakes made, lessons learned - my QuestCom CLI"
date:       2017-11-22 22:59:47 -0500
permalink:  mistakes_made_lessons_learned
---

For my CLI portfolio project I chose to make a program that would give the user the top-rated comment on a quest from the game World of Warcraft as shown on the site wowhead.com. My idea was simple, take in a quest name, return the body of the highest-rated comment from wowhead with options to show a list for all of that quest's comments, more info about any one comment, do a new search or exit the program. 

Simple, right? Well it ended up being a bit more complicated than I thought to wrangle a site's javascript response into nice-looking text. Once I was near done with the program, I went back to the project's instructions and my heart sank. I completely forgot about part of the assignment, my commit messages were crap.

As we are all human, we all make mistakes. If we learn something from the mistake, is it not then a knowledge gain? This cli portfolio project gave me many 'knowledge gains' along the way and I felt crippled by the perceived weight of the whole thing: my first portfolio project ever at a point where I don't yet feel confident in what I know about writing code. I was scared, to be honest. Maybe that fear resulted my oversight, not reminding myself along the way of what all the requirements were, who knows but I know now that the fear is silly. I'm still learning and of course there will be mistakes and that's ok. Get up and keep trying! So, since I neglected to make every commit message clear, accurate and relevant, I would like to use this space to elaborate on those messages and talk about my experience with this project. 

[(link to commits: beginning at oldest)](https://github.com/nerdybug/quest_com/commits/master?after=8033eb9ec26ed9ed8950aa7b9afa2c63179d55c5+104)

* <font size="2">"construction" Aug 6 - initialize program in bin file, require program files in quest_com.rb, start class files</font>

* <font size="2">"flesh out CLI and start Scraper" Aug 6 - define #call, #greet, #get_quest_name and #scrape_for_id in CLI; define #initialize in Scraper</font>

* <font size="2">"add methods to prepare and search with user input" Aug 7 - define #prepare_input_for_search, #search_for_result_body, #parse_quest_id and add to #initialize in Scraper</font>
 
* <font size="2">"begin QuestData class logic and add Scraper method to find quest data: Aug 9 - define #initialize, #find_all_comments and #find_top_comment in QuestData; define #find_data_from_quest_page and #scrape_to_create_quest_object in Scraper; add scraper calls to CLI #scrape_for_id and change to printed info in CLI #get_quest_name for testing</font>

* <font size="2">"extract html data for each comment" Aug 10 - Scraper work: require nokogiri and open-uri; replace #find_data_from_quest_page with #find_comments_on_quest_page; add sleep and QuestData object creation to #crape_to_create_quest_object</font>
 
* <font size="2">"some updates" Aug 19 - change bundled summary, description, homepage and metadata in gemspec</font>

* <font size="2">"changes to required gems" Aug 19 - replace use of nokogiri and open-uri with json and ostruct</font>

* <font size="2">"show top comment" Aug 19 - add call for #top_comment in CLI #scrape_for_id</font>

* <font size="2">"begin display of top comment" Aug 19 - QuestData work: change data given to #initialize using OpenStruct objects, add line to test printing number of comments a quest has, replace #find_all_comments with #all_comments, change name of #find_top_comment to #top_comment, add printing of index 0 comment's body</font>

* <font size="2">"locate js response with comments, convert to json, create comments" Aug 19 - Scraper work: extract lines to gather js response from #search_for_result_body into new #hit_this_url, change #find_comments_on_quest_page to use match regex to extract comments data from js response and convert that data to json, define #testing_ostruct_for_comments</font>

* <font size="2">"remove openstruct" Aug 22 - change name of comment data related instance variables in QuestData</font>

* <font size="2">"comment edits" Aug 23 - edit comment notes in Scraper #convert_to_json, #find_comments_on_quest_page and #testing_ostruct_for_comments</font>

* <font size="2">"create Comment class and initial methods" Aug 23 - add Comment class, define Comment #initialize, #fix_date, #more_information</font>

* <font size="2">"adjust creation of comment objects and top comment access" Aug 23 - QuestData work: remove #top_comment, add top_comment instance variable and attribute, define #create_and_store_comments with all_comments instance variable</font>

* <font size="2">"shows top comment" Aug 23 - CLI work: change #scrape_for_id to #scrape_for_quest_data, define #show_top_comment</font>

* <font size="2">"edit comments" Aug 23 - edit comment notes in Scraper #hit_this_url and #search_for_result_body</font>

* <font size="2">"add options" Aug 23 - CLI work: remove unneeded comment notes, define #top_options</fo

* <font size="2">"relocate some logc to QuestData clas" Aug 24 - CLI work: change call of #top_comment and #options; remove #show_top_comment and #top_options</font>

* <font size="2">"edit comments" Aug 24 - edit comment notes in Comment class</font>

* <font size="2">"acquired logic from CLI" Aug 24 - QuestData work: add #show_top_comment and #options from CLI, define #reset and #other_comments</font>

* <font size="2">"initial menu" Aug 25 - change #options call to #initial_menu in CLI</font>

* <font size="2">"current and top_comment indicators" Aug 25 - Comment work: add current and top_comment attributes, add notes about the attributes, define #top?, use heredoc in #more_information</font>

* <font size="2">"menu construction" Aug 25 - QuestData work: remove top_comment attribute, replace #options with #menu, define #initial_menu, #find_current_comment, #get_all_comments and #analyze_input</font>

* <font size="2">"handling content display" Aug 26 - Comment work: change format of heredoc in #more_information and add temporary #snippet</font>

* <font size="2">"work on comment body: Aug 26 - define #clean_body in Comment</font>

* <font size="2">"reduce sleep" Aug 26 - reduce sleep duration in Scraper #scrape_to_create_quest_object</font>

* <font size="2">"continue comment body work" Aug 26 - Comment work: add commentid attribute, add notes to class and #top?, add more regexes to #clean_body</font>

* <font size="2">"add sleep, change comments list" Aug 26 - QuestData work: change printed text in #initialize, add sleep and change construction in #all_comments_list, add sleep to #initial_menu </font>

* <font size="2">"small edit" Aug 30 - small edit to printed text in QuestData #menu</font>

* <font size="2">"alter regex o input" Aug 30 - change regex for input in Scraper #prepare_input_for_search</font>

* <font size="2">"edit comments, work on parsing" Aug 30 - Scraper work: remove unneeded comment notes, add test using json stringify</font>

* <font size="2">"conversion gsub neeeds fixing" Aug 31 - Scraper work: add comment notes to #convert_to_json, remove json stringify</font>

* <font size="2">"working on preparation of javascript response" Aug 31 - Scraper work: change #convert_to_json to #tidy_for_json, add regexes to #tidy_for_json</font>

* <font size="2">"alter regex for conversion prep, needs work" Sep 6 - change regexes in Scraper #tidy_for_json</font>

* <font size="2">"change variable" Sep 7 - change result variable to javascript variable in Scraper #tidy_for_json</font>

* <font size="2">"tidy for json methodis working" Sep 7 - change regexes and add comment notes in Scraper #tidy_for_json</font>

* <font size="2">"add readline" Sep 9 - require readline, add readline call to CLI</font>

* <font size="2">"change how top comment s found" Sep 10 - remove top_comment attribute and #top? from Comment, change how top comment is located in QuestData #show_top_comment</font>

* <font size="2">"allow number selection from comment list" Sep 10 - QuestData work: define #order_comments and #show_selected, rearrange sleeps, add numeral input in #analyze_input</font>

* <font size="2">"change handling of current comment" Sep 10 - define #clear_current_comment in QuestData, change comments variable to #get_all_comments call</font>

* <font size="2">"change info options" Sep 10 - define #info in QuestData</font>

* <font size="2">"remove unwanted scraped data" Sep 10 - remove unneeded comment notes in Comment; add regexes to remove unwanted scraped data in Scraper #tidy_for_json</font>

* <font size="2">"get rid of userrating" Sep 11 - remove userrating attribute from Comment; consolidate regexes in Scraper #tidy_for_json</font>

* <font size="2">"add handler" Sep 11 - add Handler class, move #greet from CLI to Handler</font>

* <font size="2">"tighten cli" Sep 11 - remove #scrape_for_quest_data from CLI</font>

* <font size="2">"remove comment" Sep 11 - remove unneeded #initial_menu from QuestData</font>

* <font size="2">"use handler for scraped data" Sep 12 - add #tidy_for_json, #analyze_matches and #prepare_input to Handler; replace moved methods with Handler calls in Scraper</font>

* <font size="2">"remove unneeded method" Sep 12 - replace #prepare_input_for_search in Scraper with Handler call</font>

* <font size="2">"remove unneeded method" Sep 12 - remove #prepare_input_for_search from Scraper</font>

* <font size="2">"use handler for quest data" Sep 12 - add #puts_menu, #prints_top, #prints_selected, #current_info, #try_again and #goodbye to Handler; replace printing logic with Handler calls in QuestData</font>

* <font size="2">"use handler for comment data" Sep 13 - replace regexes in Comment with Handler calls; add #comment_info, #assemble_list, #snip, #clean and #shorten to Handler; add comment notes in QuestData and use Handler call in #all_comments_list</font>

* <font size="2">"changesto scraper.new" Sep 13 - change #scrape_to_create_quest_object to #from_input_to_quest in Scraper and comment out #initialize; use new #from_input_to_quest in CLI</font>

* <font size="2">"body work" Sep 13 - define #match_comments_variable in Handler; replace variable regex matching in Scraper with Handler call</font>

* <font size="2">"begin npc name replacement" Sep 14 - define #npc_replace in Handler</font>

* <font size="2">"add nokogiri and open uri" Sep 14 - require nokogiri and open uri again</font>

* <font size="2">"npc name replacement works" Sep 14 - define #npc_name in Scraper; add to #npc_replace in Handler to replace an npc tag with a scraped name</font>

* <font size="2">"replacing quest and item brackets with names" Sep 14 - define #quest_replace, #get_names and #item_replace in Handler; define #find_name and replace #npc_name in Scraper</font>

* <font size="2">"fixed snipped" Sep 14 - fix #snippet in Comment to not change the whole comment's body</font>

* <font size="2">"edits to initial readout" Sep 14 - define #load_msg in Handler; change Handler call in QuestData #show_selected; add Handler call for loading message in Scraper #from_input_to_quest</font>

* <font size="2">"replaces many bracketed wowhead ids" Sep 14 - Handler work: change #get_names to #mass_replace</font>

* <font size="2">"change when text is cleaned" Sep 14 - comment out clean_body call in Comment #initialize and use Handler calls to snip and clean in #snippet; change to load message wording in Handler, also add sleep and load message to #assemble_list; add cleaning to #show_top_comment in QuestData and #show_selected</font>

* <font size="2">"tweaks to body handling" Sep 20 - Handler work: move line breaks in printed messages, add regex for hr tags, change #get_names to #replace_names; Scraper work: remove unneeded #initialize and #npc_name, add URI escape in #find_name</font>

* <font size="2">"fix snippet" Sep 20 - add #clean_body call to #snippet in Comment, remove #clean_body call in QuestData #show_selected</font>

* <font size="2">"changes to handler use" Sep 20 -  Handler work: add quest_data attribute, define #initialize, #find_length_of_comments, #assemble_list and #puts_menu, change some class methods to instance methods; QuestData work: add handler attribute, change #create_and_store_comments to #create_and_save_comments, define #handle, replace Handler calls with #handle calls</font>

* <font size="2">"more changes to handler" Sep 20 - Handler work: define #comments, #data, #show_selected, #show_top, #analyze_input, #try_again and #goodbye, change printed text in #load_msg; QuestData work: comment out #all_comments_list, #show_top_comment, #show_selected, #menu and #analyze_input</font>

* <font size="2">"removed unneeded comments" Sep 20 - remove commented out note and #prints_selected from Handler; remove unneeded #all_comments_list, #show_top_comment, #show_selected, #menu and #analyze_input from QuestData</font>

* <font size="2">"more handler changes" Sep 20 - move #info, #clear_current_comment and #find_current_comment from QuestData to Handler, change #comment_info from class method to instance method</font>

* <font size="2">"fix snippet" Sep 20 - remove #clean_body call from #snippet in Comment, use Handler to clean snippet content</font>

* <font size="2">"changes to output format" Sep 20 - Handler work: edit printed text content in #menu, #comment_info, #try_again, #goodbye, #load_msg, #load_msg, #greet_user and #prepare_input</font>

* <font size="2">"removed reset" Sep 21 - remove #reset call in Handler #analyze_input</font>

* <font size="2">"removed reset, remove comment_data var" Sep 21 - QuestData work: comment out #reset, change parameter name for #create_and_save_comments</font>

* <font size="2">"removed get all comments" Sep 21 - Handler work: remove #find_length_of_comments and change all comments method call; QuestData work: change attribute reader to accessor, remove unneeded #reset, move #get_all_comments logic to #order_comments</font>

* <font size="2">"chaes to options handling" Sep 21 - Handler work: define #too_many_matches, #no_matches and #new_or_exit, change #goodbye from class method to instance method, add exit option to printed content in #greet_user</font>

* <font size="2">"hanno comments" Sep 21 - define #no_comments and add call within #match_comments_variable in Handler</font>

* <font size="2">"fixes to body cleaning" Sep 23 - add #clean call to #show_selected and change regex for urls in Handler</font>

* <font size="2">"fixes to body" Sep 23 - Handler work: add comment notes, remove quotes around printed top comment, change regex replacement text for removed tables, add regex to handle quote tags</font>

* <font size="2">"add comments" Sep 24 - Comment work: remove commented out #clean_body calls, add comment note; Handler work: add and edit comment notes, remove unneeded comment notes, change clean text method call, change boolean expression when checking for numeral input in #analyze_input; QuestData work: remove unneeded quest_id variable, add comment note; Scraper work: add and edit comment notes</font>

* <font size="2">"restructuring" Sep 26 - change CLI #start call in QuestCom bin; move some methods from Handler and Scraper to new QuestCom module (#prepare_input, #analyze_quest_matches, #match_comments_variable, #tidy_for_json); move some methods from Handler to CLI (#greet_user, #load_msg, #new_or_exit, #too_many_matches, #no_matches, #no_comments, goodbye); comment out moved methods</font>

* <font size="2">"restructuring" Sep 27 - move #assemble_list to CLI, define #show_info in Comment, move #comment_info from Handler to CLI, add current attribute in Comment</font>

* <font size="2">"using module methods" Sep 28 - define #analyze and change #analyze_quest_matches to #find_quest_matches in QuestCom, call #analyze in #parse_quest_id and #find_comments_on_quest_page in Scraper</font>

* <font size="2">"using module methods" Sep 28 - move #from_input_to_quest from Scraper to QuestCom, CLI work: include QuestCom, call #from_input_to_quest in #start; Handler work: remove unneeded methods, comment out #show_top, use CLI to call #menu; QuestData work: remove unneeded #assemble_list, define #get_comments, add #show_top from Handler; Scraper work: extend QuestCom</font>

* <font size="2">"using module methods" Oct 5 - move methods from Handler to QuestCom (#get_snip, #clean, #mass_replace, #find_and_replace, replace_names, #shorten), CLI (#try_again) and QuestData (#show_selected, #list_comments which was #assemble_list, #clear_current_comment, #user_picks which was #menu); remove #handle and handler attribute from QuestData; use #analyze calls to replace Handler calls in Comment</font>

* <font size="2">"misc fixes" Oct 7 - CLI work: require readline, extend QuestCom, add to printed text in #start; Comment  work: include QuestCom; QuestData work: add #find_current_comment and #info from Handler</font>

* <font size="2">"removed file" Oct 7 - removed Handler class file</font>


And there you have it. Did I learn a great many things while working on this project? Yes. Will I ever make a mistake again? Probably, I am no Sophia Robot (who is fascinating - look her up if you haven't heard of her). Due to the time spent thinking about and working on this project, it's clear that being stubborn about asking for help instead of trying to figure it out is the number one way to spend entirely too much time on something. From all my years as a human, I've preferred to find answers on my own but this new realm that I'm learning to walk in is different. If, dear reader, you are still with me here at the end of this massive post, remember this: don't forget to *not* forget the instructions!


