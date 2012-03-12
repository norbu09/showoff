!SLIDE 
# Jenkins #

!SLIDE center

![jenkins](jenkins.png)

!SLIDE
# convince Jenkins to test Perl #

    TAP::Formatter::JUnit


!SLIDE
# the full glory #

    @@@ sh
    prove -r -Ilib --timer \
        --formatter=TAP::Formatter::JUnit \
        -l t > test_results.xml

!SLIDE
# Post-build Actions #

![post-build](post_build.png)

!SLIDE center

![tests1](tests1.png)

!SLIDE center

![tests2](tests2.png)

!SLIDE center

![tests3](tests3.png)

!SLIDE center

![tests4](tests4.png)

!SLIDE
# let the magic happen #

![post-build-script](post-build-script.png)

