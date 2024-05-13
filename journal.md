
# Table of Contents

1.  [2024](#org8a6f130)
    1.  [2024-01 January](#org541a537)
        1.  [2024-01-17 Wednesday](#orgbba9d2a)
        2.  [2024-01-18 Thursday](#orgecd2bb2)
        3.  [2024-01-19 Friday](#orgb346c7e)
        4.  [2024-01-22 Monday](#org31d811e)
    2.  [2024-05 May](#org6ffc0fb)
        1.  [2024-05-13 Monday](#org8a37fe2)



<a id="org8a6f130"></a>

# 2024


<a id="org541a537"></a>

## 2024-01 January


<a id="orgbba9d2a"></a>

### 2024-01-17 Wednesday

1.  Onboarding Notes 'OpenSYDE Plugins (J1939)'

    1.  Added to project <span class="timestamp-wrapper"><span class="timestamp">[2024-01-17 Wed 13:20]</span></span>
    
        1.  DONE Next Actions <code>[8/8]</code> <span class="timestamp-wrapper"><span class="timestamp">&lt;2024-01-17 Wed 17:35&gt;</span></span>
        
            -   [X] Refer to the How-to prepared by TG
            -   [X] Download and install "i686-8.1.0-release-posix-dwarf-rt\_v6-rev0.7z"
            -   [X] Download and install "openSYDE\_Release 22-0B(v1.42r0).zip"
            -   [X] Download and install "qt-creator-opensource-windows-x86\_64-4.14.2.exe"
            -   [X] Download and install "qt-unified-windows-x86-4.3.0-1-online.exe"
            -   [X] Setup user account with QT
            -   [X] clone github repo <https://github.com/STW-Technic-LP/J1939Plugin>
            -   [X] start a documentaion journal for onboarding process.
            
            Entered on <span class="timestamp-wrapper"><span class="timestamp">[2024-01-17 Wed 15:18]</span></span>

2.  Toolchain setup

    -   Minor confustion on version.  Text of pdf says 15.5.2, URL in pdf goes to 14.4.2 (newer than 15.5.2?)
    -   TG confirmed target version is 15.5.2.  Used web installer to choose 'custom install' and selected 15.5.2
    -   Took a couple trie to get install correct. <span class="timestamp-wrapper"><span class="timestamp">[2024-01-17 Wed 16:29]</span></span>
    -   QT Creator installed, Mingw 8.1 configured, J1939 github project cloned
    -   Left off at <span class="timestamp-wrapper"><span class="timestamp">[2024-01-17 Wed 17:35] </span></span> with J1939 github project opened inside of QT Creator.  Contact TG for next step.
    
    Entered on <span class="timestamp-wrapper"><span class="timestamp">[2024-01-17 Wed 15:31]</span></span>


<a id="orgecd2bb2"></a>

### 2024-01-18 Thursday

1.  Toolchain setup continued

    1.  DONE Next Actions <code>[2/2]</code>
    
        -   [X] Import, Open, and Build openSYDE using Qt Creator
            -   FAILED: 1st attempt would not build, Qt stopped build process, error indicated missing files
            -   FAILED: Per TG, turned off 'Shadow Build' still failed.
            -   PASSED: Possible 260 char limit of path / filenames issue.  Moved project up higher in C:/. Build OK
            -   NOTE: created Qt projects directory under `C:\stw\qtProjects` to minimize char length and eliminate spaces in directory name.
                prior folder was in a OneDrive managed user folder. `C:\Users\silas.curfman\OneDrive - STW Technic LP\Documents\_PROJECTS>`
        -   [X] Run freshly built openSYDE project.
            -   PASSED/FAILED: Application correctly launched an instance of openSYDE but upon viewing About, version was 1.6.0.
                We needed v1.42.0r.  TG set out to get new files.
            -   PASSED: New .zip project imported, built, and ran successfully
        
        Entered on <span class="timestamp-wrapper"><span class="timestamp">[2024-01-18 Thu 15:28]</span></span>


<a id="orgb346c7e"></a>

### 2024-01-19 Friday

1.  Plug-in Project Review

    -   With current .pro correctly running in Qt Creator, take time to explore both Qt and the code base.
    
    1.  DONE Next Actions <code>[4/4]</code>
    
        -   [X] Complete Qt built in new user tour
        -   [X] Explore the file / folder structure of the project
        -   [X] Run the compiled binary, explore the version of openSYDE it launches
        -   [X] To see the plugin, need to import in some devices, copy over from your production copy of openSYDE.
    
    2.  DONE Topic / Reference Review <code>[7/7]</code>
    
        -   [X] J1939 DBC
        -   [X] J1939 PGN
        -   [X] J1939 SPN
        -   [X] dbc\_driver\_library on openSYDE github project.
        -   [X] visit Vector Informatik, DBC related info
        -   [X] where is UI info for J1939 plugin defined?  <span class="timestamp-wrapper"><span class="timestamp">[2024-01-19 Fri 17:46] </span></span>
        -   [X] revisit C\_Sd\_BueComlfDescriptionWidget in Qt, "page" or tab 5/5 is J1939 UI. <span class="timestamp-wrapper"><span class="timestamp">[2024-01-19 Fri 17:52] </span></span>
        
        Entered on <span class="timestamp-wrapper"><span class="timestamp">[2024-01-19 Fri 09:06]</span></span>


<a id="org31d811e"></a>

### 2024-01-22 Monday

1.  Qt Creator 12 onboarding

    Entered on <span class="timestamp-wrapper"><span class="timestamp">[2024-01-22 Mon 07:30]</span></span>


<a id="org6ffc0fb"></a>

## 2024-05 May


<a id="org8a37fe2"></a>

### 2024-05-13 Monday

1.  Weekly Planning

    1.  TODO New Flyer <code>[0/3]</code>
    
        -   [ ] Jira review
        -   [ ] Meet with KB, monday
        -   [ ] Meet with JG, tuesday
    
    2.  TODO GCP+Verifi <code>[/]</code>
    
        -   [ ] Jira review
    
    3.  TODO Distek ISOBUS <code>[0/2]</code>
    
        -   [ ] Jira review
        -   [ ] Check for tracking number, display from JG
    
    4.  TODO J1939 Plugin <code>[0/2]</code>
    
        -   [ ] Jira review
        -   [ ] Meeting with TG, monday
    
    5.  TODO Misc <code>[0/2]</code>
    
        -   [ ] Meet with AR, paycor Wednesday
        -   [ ] Home Office Maint
            -   [ ] misc tooling
            -   [ ] install more shelf space
            -   [ ] replace router / wifi
            -   [ ] segment network
            -   [ ] janitorial (vacuum, etc)
        
        Entered on <span class="timestamp-wrapper"><span class="timestamp">[2024-05-13 Mon 07:30]</span></span>

