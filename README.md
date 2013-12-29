gostdc provides C Standard Library (alias libc) for porting legacy C programs to compile with [the Go compiler suite][goc].

**NOTE:** Work In Progress. I use it in the [goluago][goluago] project to some success, but it may have some lurking bugs. It has only rudimentary test coverage, so I make no guarantees, Use At Your Own Risk, it may eat your homework, kill your kittens, etc., etc.

  [goc]: http://golang.org/cmd/cc/
  [goluago]: http://github.com/akavel/goluago

[![Build Status](https://secure.travis-ci.org/akavel/gostdc.png)](http://travis-ci.org/akavel/gostdc) - includes *some* unit tests.

QUICK USAGE
-----------

  * `go get github.com/akavel/gostdc`
  * `cd github.com/akavel/gostdc`
  * `cp copy_me/*.h $MY_PROJECT/`
  * edit `$MY_PROJECT/gostdc.h` to make sure it has right number of `../` segments
  * in some Go file `$MY_PROJECT/*.go` add: `import _ "github.com/akavel/gostdc"`

CHANGELOG
---------

  * 2013.12.29: published an internal "fork" based on [Plan 9 "APE" POSIX libraries + libc][APE] (thanks to Lars Seipel for info on those)

  [APE]: http://plan9.bell-labs.com/sys/doc/ape.html

TODO
----

  * slap license on the files + add AUTHORS file.
  * write full pretty readme
  * fix all FIXMEs and/or reuse some MIT/BSD implementations
  * extend the library to cover all of Standard C Library
  * [optionally] replace most C functions with some MIT/BSD
    implementations
  * split the .c and .go files functionally as .h files would suggest
  * add info that you **must** make sure **every single** C file does
    effectively `#include "gostdc.h"`, [because of][1]
    ["extern register"][plan9cc]

  [1]: https://code.google.com/p/go/source/diff?spec=svn9ef1fd2b7e476df9c04fec3c9833fe473cbacc42&name=9ef1fd2b7e47&r=9ef1fd2b7e476df9c04fec3c9833fe473cbacc42&format=side&path=/src/pkg/runtime/runtime.h#sc_svn9ef1fd2b7e476df9c04fec3c9833fe473cbacc42_94
  [plan9cc]: http://doc.cat-v.org/plan_9/4th_edition/papers/compiler

LICENSE
-------

**NOTE:**
This code in its current form is mostly composed of verbatim copy of parts of [Plan9 APE][APE] code. From a high level point of view, it should be thus seen as licensed under "Lucent Public License Version 1.02", as provided below.

However, some small parts of the code are my additions; those parts (and only those) are MIT-licensed, as listed in an appropriate section near the end of this very README.md file.

### "Lucent Public License Version 1.02" - which covers most of this code:

Note: this license is reportedly "OSI and FSF approved, although not compatible with GPL" (see [Lucent Public License on Wikipedia](https://en.wikipedia.org/wiki/Lucent_Public_License)).

**WITH EXCEPTION OF FILES LISTED IN NEXT SECTION (which are MIT-licensed), files in this repository are licensed as specified below:**

Lucent Public License Version 1.02

THE ACCOMPANYING PROGRAM IS PROVIDED UNDER THE TERMS OF THIS PUBLIC
LICENSE ("AGREEMENT"). ANY USE, REPRODUCTION OR DISTRIBUTION OF THE
PROGRAM CONSTITUTES RECIPIENT'S ACCEPTANCE OF THIS AGREEMENT.

1. DEFINITIONS

"Contribution" means:

  a. in the case of Lucent Technologies Inc. ("LUCENT"), the Original
     Program, and
  b. in the case of each Contributor,

     i. changes to the Program, and
    ii. additions to the Program;

    where such changes and/or additions to the Program were added to the
    Program by such Contributor itself or anyone acting on such
    Contributor's behalf, and the Contributor explicitly consents, in
    accordance with Section 3C, to characterization of the changes and/or
    additions as Contributions.

"Contributor" means LUCENT and any other entity that has Contributed a
Contribution to the Program.

"Distributor" means a Recipient that distributes the Program,
modifications to the Program, or any part thereof.

"Licensed Patents" mean patent claims licensable by a Contributor
which are necessarily infringed by the use or sale of its Contribution
alone or when combined with the Program.

"Original Program" means the original version of the software
accompanying this Agreement as released by LUCENT, including source
code, object code and documentation, if any.

"Program" means the Original Program and Contributions or any part
thereof

"Recipient" means anyone who receives the Program under this
Agreement, including all Contributors.

2. GRANT OF RIGHTS

 a. Subject to the terms of this Agreement, each Contributor hereby
    grants Recipient a non-exclusive, worldwide, royalty-free copyright
    license to reproduce, prepare derivative works of, publicly display,
    publicly perform, distribute and sublicense the Contribution of such
    Contributor, if any, and such derivative works, in source code and
    object code form.
    
 b. Subject to the terms of this Agreement, each Contributor hereby
    grants Recipient a non-exclusive, worldwide, royalty-free patent
    license under Licensed Patents to make, use, sell, offer to sell,
    import and otherwise transfer the Contribution of such Contributor, if
    any, in source code and object code form. The patent license granted
    by a Contributor shall also apply to the combination of the
    Contribution of that Contributor and the Program if, at the time the
    Contribution is added by the Contributor, such addition of the
    Contribution causes such combination to be covered by the Licensed
    Patents. The patent license granted by a Contributor shall not apply
    to (i) any other combinations which include the Contribution, nor to
    (ii) Contributions of other Contributors. No hardware per se is
    licensed hereunder.
    
 c. Recipient understands that although each Contributor grants the
    licenses to its Contributions set forth herein, no assurances are
    provided by any Contributor that the Program does not infringe the
    patent or other intellectual property rights of any other entity. Each
    Contributor disclaims any liability to Recipient for claims brought by
    any other entity based on infringement of intellectual property rights
    or otherwise. As a condition to exercising the rights and licenses
    granted hereunder, each Recipient hereby assumes sole responsibility
    to secure any other intellectual property rights needed, if any. For
    example, if a third party patent license is required to allow
    Recipient to distribute the Program, it is Recipient's responsibility
    to acquire that license before distributing the Program.

 d. Each Contributor represents that to its knowledge it has sufficient
    copyright rights in its Contribution, if any, to grant the copyright
    license set forth in this Agreement.

3. REQUIREMENTS

A. Distributor may choose to distribute the Program in any form under
this Agreement or under its own license agreement, provided that:

 a. it complies with the terms and conditions of this Agreement;

 b. if the Program is distributed in source code or other tangible
    form, a copy of this Agreement or Distributor's own license agreement
    is included with each copy of the Program; and

 c. if distributed under Distributor's own license agreement, such
    license agreement:

      i. effectively disclaims on behalf of all Contributors all warranties
         and conditions, express and implied, including warranties or
         conditions of title and non-infringement, and implied warranties or
         conditions of merchantability and fitness for a particular purpose;
     ii. effectively excludes on behalf of all Contributors all liability
         for damages, including direct, indirect, special, incidental and
         consequential damages, such as lost profits; and
    iii. states that any provisions which differ from this Agreement are
         offered by that Contributor alone and not by any other party.

B. Each Distributor must include the following in a conspicuous
   location in the Program:

   Copyright (C) 2003, Lucent Technologies Inc. and others. All Rights
   Reserved.

C. In addition, each Contributor must identify itself as the
originator of its Contribution in a manner that reasonably allows
subsequent Recipients to identify the originator of the Contribution.
Also, each Contributor must agree that the additions and/or changes
are intended to be a Contribution. Once a Contribution is contributed,
it may not thereafter be revoked.

4. COMMERCIAL DISTRIBUTION

Commercial distributors of software may accept certain
responsibilities with respect to end users, business partners and the
like. While this license is intended to facilitate the commercial use
of the Program, the Distributor who includes the Program in a
commercial product offering should do so in a manner which does not
create potential liability for Contributors. Therefore, if a
Distributor includes the Program in a commercial product offering,
such Distributor ("Commercial Distributor") hereby agrees to defend
and indemnify every Contributor ("Indemnified Contributor") against
any losses, damages and costs (collectively"Losses") arising from
claims, lawsuits and other legal actions brought by a third party
against the Indemnified Contributor to the extent caused by the acts
or omissions of such Commercial Distributor in connection with its
distribution of the Program in a commercial product offering. The
obligations in this section do not apply to any claims or Losses
relating to any actual or alleged intellectual property infringement.
In order to qualify, an Indemnified Contributor must: a) promptly
notify the Commercial Distributor in writing of such claim, and b)
allow the Commercial Distributor to control, and cooperate with the
Commercial Distributor in, the defense and any related settlement
negotiations. The Indemnified Contributor may participate in any such
claim at its own expense.

For example, a Distributor might include the Program in a commercial
product offering, Product X. That Distributor is then a Commercial
Distributor. If that Commercial Distributor then makes performance
claims, or offers warranties related to Product X, those performance
claims and warranties are such Commercial Distributor's responsibility
alone. Under this section, the Commercial Distributor would have to
defend claims against the Contributors related to those performance
claims and warranties, and if a court requires any Contributor to pay
any damages as a result, the Commercial Distributor must pay those
damages.

5. NO WARRANTY

EXCEPT AS EXPRESSLY SET FORTH IN THIS AGREEMENT, THE PROGRAM IS
PROVIDED ON AN"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, EITHER EXPRESS OR IMPLIED INCLUDING, WITHOUT LIMITATION, ANY
WARRANTIES OR CONDITIONS OF TITLE, NON-INFRINGEMENT, MERCHANTABILITY
OR FITNESS FOR A PARTICULAR PURPOSE. Each Recipient is solely
responsible for determining the appropriateness of using and
distributing the Program and assumes all risks associated with its
exercise of rights under this Agreement, including but not limited to
the risks and costs of program errors, compliance with applicable
laws, damage to or loss of data, programs or equipment, and
unavailability or interruption of operations.

6. DISCLAIMER OF LIABILITY

EXCEPT AS EXPRESSLY SET FORTH IN THIS AGREEMENT, NEITHER RECIPIENT NOR
ANY CONTRIBUTORS SHALL HAVE ANY LIABILITY FOR ANY DIRECT, INDIRECT,
INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING
WITHOUT LIMITATION LOST PROFITS), HOWEVER CAUSED AND ON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OR
DISTRIBUTION OF THE PROGRAM OR THE EXERCISE OF ANY RIGHTS GRANTED
HEREUNDER, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.

7. EXPORT CONTROL

Recipient agrees that Recipient alone is responsible for compliance
with the United States export administration regulations (and the
export control laws and regulation of any other countries).

8. GENERAL

If any provision of this Agreement is invalid or unenforceable under
applicable law, it shall not affect the validity or enforceability of
the remainder of the terms of this Agreement, and without further
action by the parties hereto, such provision shall be reformed to the
minimum extent necessary to make such provision valid and enforceable.

If Recipient institutes patent litigation against a Contributor with
respect to a patent applicable to software (including a cross-claim or
counterclaim in a lawsuit), then any patent licenses granted by that
Contributor to such Recipient under this Agreement shall terminate as
of the date such litigation is filed. In addition, if Recipient
institutes patent litigation against any entity (including a
cross-claim or counterclaim in a lawsuit) alleging that the Program
itself (excluding combinations of the Program with other software or
hardware) infringes such Recipient's patent(s), then such Recipient's
rights granted under Section 2(b) shall terminate as of the date such
litigation is filed.

All Recipient's rights under this Agreement shall terminate if it
fails to comply with any of the material terms or conditions of this
Agreement and does not cure such failure in a reasonable period of
time after becoming aware of such noncompliance. If all Recipient's
rights under this Agreement terminate, Recipient agrees to cease use
and distribution of the Program as soon as reasonably practicable.
However, Recipient's obligations under this Agreement and any licenses
granted by Recipient relating to the Program shall continue and
survive.

LUCENT may publish new versions (including revisions) of this
Agreement from time to time. Each new version of the Agreement will be
given a distinguishing version number. The Program (including
Contributions) may always be distributed subject to the version of the
Agreement under which it was received. In addition, after a new
version of the Agreement is published, Contributor may elect to
distribute the Program (including its Contributions) under the new
version. No one other than LUCENT has the right to modify this
Agreement. Except as expressly stated in Sections 2(a) and 2(b) above,
Recipient receives no rights or licenses to the intellectual property
of any Contributor under this Agreement, whether expressly, by
implication, estoppel or otherwise. All rights in the Program not
expressly granted under this Agreement are reserved.

This Agreement is governed by the laws of the State of New York and
the intellectual property laws of the United States of America. No
party to this Agreement will bring a legal action under this Agreement
more than one year after the cause of action arose. Each party waives
its rights to a jury trial in any resulting litigation.


### Parts of the code are MIT-licensed:

  * `copy_me/*`
  * `hdrs/*gostdc*`
  * `.travis.yml`
  * `*_test.c`
  * `gostdc*`

**The files matching patterns listed above are MIT-licensed, as specified below:**


Copyright (c) 2011-2013 Mateusz Czapliński

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
