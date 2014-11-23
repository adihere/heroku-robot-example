*** Settings ***
Documentation     Sample test suite project with one test suite and one test case.
...
...               Contains also two scalar variables for default web page and browser to use.
Library           Selenium2Library

*** Variables ***
${browser}        ff    # Web browser to use for testing. Can be overriden from command line.
${web-page}       http://google.com    # Web page to open for testing.

*** Test Cases ***
TestCase
    [Setup]    Open Browser	${web-page}    browser=${browser}
    Wait Until Page Contains    Google     15
    [Teardown]    Close Browser
