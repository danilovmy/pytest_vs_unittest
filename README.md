# pytest_vs_unittest
## repository for presenting advantages of unittest

Discussion is here:
https://www.linkedin.com/feed/update/urn:li:groupPost:101591-7222650080351113217?commentUrn=urn%3Ali%3Acomment%3A%28groupPost%3A101591-7222650080351113217%2C7222727112191823872%29&replyUrn=urn%3Ali%3Acomment%3A%28groupPost%3A101591-7222650080351113217%2C7224437412356046850%29&dashCommentUrn=urn%3Ali%3Afsd_comment%3A%287222727112191823872%2Curn%3Ali%3AgroupPost%3A101591-7222650080351113217%29&dashReplyUrn=urn%3Ali%3Afsd_comment%3A%287224437412356046850%2Curn%3Ali%3AgroupPost%3A101591-7222650080351113217%29

## My thoughts:

1. Unittest has better error messages, this is no joke.

Although pytest is very verbose in describing errors,
unittest provides a more informative "default" error message.

If the assertion fails, `self.assertTrue(obj)` produces the message "obj is not true",
which is more informative than PyTest AssertionError.


2. unittest is more explicit:
`self.assertTrue(obj)` is more explicit and clear than `assert obj`
This improves the readability, maintainability and clarity of the code.
Unittest requires from developer a more explicit declaration of what exactly is supposed to be tested, this increases also the testing understanding of the developer.

3. autocomplete:
If I want to select the best assertion for the current test, I can use autocomplete.
I can see the list of assertions and select the best one for the current test.

4. consistency:
If the assertion is aligned with the idea of the test - I can visualize what the developer wants to do in the test.
Many developers fight over the right variable naming, and the right assertion is exactly the same.
Many developers fight over type-hinting, and the right assertion is exactly the same, too.

5. Speed
By default, without additional plugins, Pytest is 4 times slower than unittest.

In this repository you can check it out.


## to test performance of tests:
### PyTest
python -m timeit "import subprocess; subprocess.run(['pytest', 'tests'])"
1 loop, best of 5: 493 msec per loop

### Unittest
python -m timeit "import subprocess; subprocess.run(['python', '-m', 'unittest', 'discover', '-s=utests'])"
2 loops, best of 5: 119 msec per loop