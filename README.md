# utl_replace_2nd_occurance_of_a_string_with_another_string
Replace 2nd occurance of a string with another string.  Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.

    Replace 2nd occurance of a string with another string

    see
    https://tinyurl.com/y7erx748
    https://communities.sas.com/t5/Base-SAS-Programming/Replace-string-with-another-string/m-p/465626

    same result in WPS and SAS

    Replace the second occurance of 'in' with 'from'

    INPUT
    =====

      word = "I am a student in a college in a city in India to study masters   ";

     EXAMPLE OUTPUT

                                  ====
      I am a student in a college from a city in India to study masters


    PROCESS
    =======

       data _null_;

         word = "I am a student in a college in a city in India to study masters   ";

         pos=findw(word,'in',1) +1;
         pos=findw(word,'in',pos);

         word=catx(' ',substr(word,1,pos-3),'from',substr(word,32));

         put word=;

       run;quit;

    OUTPUT
    ======

       I am a student in a college from a city in India to study masters


    SOLUTION
    ========

    %utl_submit_wps64('
    libname wrk sas7bdat "%sysfunc(pathname(work))";
       data _null_;

         word = "I am a student in a college in a city in India to study masters   ";

         pos=findw(word,"in",1) +1;
         pos=findw(word,"in",pos);

         word=catx(" ",substr(word,1,pos-3),"from",substr(word,32));

         put word=;

       run;quit;
    run;quit;
    ');
