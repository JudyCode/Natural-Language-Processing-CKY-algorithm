README NLP homework2
==================
Author : Lu Zixuan
Uni : zl2348
Date: Mar 11, 2015
==================

*** HOW TO RUN ***

Homework 2 contains three forders , they are p4, p5 and p6 perspectively. Each foulder contains all the files that are needed, including:

 * main function .py files 
 * the original data files(parse_train.dat etc.)
 * a shell sciprt (run.sh) which is used for running the whole problem.

==================
PROBLEM 4:

*** FILE ***

p4.py : used to replace the word whose counts are less than 5 to be '_RARE_' and write the new version training data into a new data file called 'parse_train_rare.dat'.

input files include: count_cfg_freq.py
output files include: cfg.counts and parse_train_rare.dat


 * estimation of running time : 5seconds

==================

PROBLEM 5:

*** FILE ***

p5.py

input files include: count_cfg_freq.py
output files include:

 * estimation of running time : less than 1 minutes

*** RESULTS ***

zl2348@kathmandu:~/Downloads/homework2/p5$ sh run.sh
      Type       Total   Precision      Recall     F1 Score
===============================================================
         .         370     1.000        1.000        1.000
       ADJ         164     0.827        0.555        0.664
      ADJP          29     0.333        0.241        0.280
  ADJP+ADJ          22     0.542        0.591        0.565
       ADP         204     0.955        0.946        0.951
       ADV          64     0.694        0.531        0.602
      ADVP          30     0.333        0.133        0.190
  ADVP+ADV          53     0.756        0.642        0.694
      CONJ          53     1.000        1.000        1.000
       DET         167     0.988        0.976        0.982
      NOUN         671     0.752        0.842        0.795
        NP         884     0.625        0.524        0.570
    NP+ADJ           2     0.286        1.000        0.444
    NP+DET          21     0.783        0.857        0.818
   NP+NOUN         131     0.641        0.573        0.605
    NP+NUM          13     0.214        0.231        0.222
   NP+PRON          50     0.980        0.980        0.980
     NP+QP          11     0.667        0.182        0.286
       NUM          93     0.984        0.645        0.779
        PP         208     0.593        0.630        0.611
      PRON          14     1.000        0.929        0.963
       PRT          45     0.957        0.978        0.967
   PRT+PRT           2     0.400        1.000        0.571
        QP          26     0.647        0.423        0.512
         S         587     0.626        0.782        0.695
      SBAR          25     0.091        0.040        0.056
      VERB         283     0.683        0.799        0.736
        VP         399     0.559        0.594        0.576
   VP+VERB          15     0.250        0.267        0.258

     total        4664     0.713        0.713        0.713



==================

PROBLEM 6:

*** FILE ***

p61.py : it functions same as p4.py, replace the rare word in the new train file parse_train_vert.dat with the '_RARE_', and generate the new file "parse_train_vert_rare.dat".

p62.py : it functions similar to p5.py, just read in differernt files(generated from p61.py) and output a prediction_file1


input files include: count_cfg_freq.py, parse_vert_rare.dat, parse_dev.dat, parse_dev.key
output files include: parse_train_vert_rare.dat prediction_file1



 * estimation of running time : less than 1 minutes

*** RESULTS ***


zl2348@kathmandu:~/Downloads/homework2/p6$ sh run.sh
      Type       Total   Precision      Recall     F1 Score
===============================================================
         .         370     1.000        1.000        1.000
       ADJ         164     0.689        0.622        0.654
      ADJP          29     0.324        0.414        0.364
  ADJP+ADJ          22     0.591        0.591        0.591
       ADP         204     0.960        0.951        0.956
       ADV          64     0.759        0.641        0.695
      ADVP          30     0.417        0.167        0.238
  ADVP+ADV          53     0.700        0.660        0.680
      CONJ          53     1.000        1.000        1.000
       DET         167     0.988        0.994        0.991
      NOUN         671     0.795        0.845        0.819
        NP         884     0.617        0.548        0.580
    NP+ADJ           2     0.333        0.500        0.400
    NP+DET          21     0.944        0.810        0.872
   NP+NOUN         131     0.610        0.656        0.632
    NP+NUM          13     0.375        0.231        0.286
   NP+PRON          50     0.980        0.980        0.980
     NP+QP          11     0.750        0.273        0.400
       NUM          93     0.914        0.688        0.785
        PP         208     0.623        0.635        0.629
      PRON          14     1.000        0.929        0.963
       PRT          45     1.000        0.933        0.966
   PRT+PRT           2     0.286        1.000        0.444
        QP          26     0.650        0.500        0.565
         S         587     0.704        0.814        0.755
      SBAR          25     0.667        0.400        0.500
      VERB         283     0.790        0.813        0.801
        VP         399     0.663        0.677        0.670
   VP+VERB          15     0.294        0.333        0.312

     total        4664     0.742        0.742        0.742

***SUMMARY & MY OBSERVATION:***

we can see from the result that there is a little improvement on the totol results compared with that of problem 5. For specific types, it improves with type"NP+ADJ", "NP+DET","NP+NUM","S","SBAR","VERB","VP","VP+VERB", but hurts(decreases) in "ADJ". It makes sense since this improves the non-terminal near the root of the tree with this kind of transmission(treat each non-termial with their span as a constituents), But it somehow will hurt the precision with level of the POS.


