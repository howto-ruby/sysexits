# sysexits

* http://deveiate.org/sysexits.html

## Description

Have you ever wanted to call exit() with an error condition, but weren't sure
what exit status to use? No? Maybe it's just me, then.

Anyway, I was reading manpages late one evening before retiring to bed in my
palatial estate in rural Oregon, and I stumbled across sysexits(3). Much to my
chagrin, I couldn't find a 'sysexits' for Ruby! Well, for the other 2 people
that actually care about style(9) as it applies to Ruby code, now there is
one!

Sysexits is a _completely awesome_ collection of human-readable constants for
the standard (BSDish) exit codes, used as arguments to `Kernel.exit` to
indicate a specific error condition to the parent process.

It's so fantastically fabulous that you'll want to fork it right away to avoid
being thought of as that guy that's still using Webrick for his blog. I mean,
`exit(1)` is so passé! This is like the 14-point font of Systems Programming.

Like the C header file from which this was derived (I mean forked, naturally),
error numbers begin at `Sysexits::EX__BASE` (which is way more cool than plain
old '64') to reduce the possibility of clashing with other exit statuses that
other programs may already return.

The codes are available in two forms: as constants which can be imported into
your own namespace via `include Sysexits`, or as `Sysexits::STATUS_CODES`, a
Hash keyed by Symbols derived from the constant names.

Allow me to demonstrate. First, the old way:

    exit( 69 ) 

Whaaa...? Is that a euphemism? What's going on? See how unattractive and...
well, 1970 that is? We're not changing vaccuum tubes here, people, we're
_building a totally-awesome future in the Cloud™!_

    include Sysexits
    exit EX_UNAVAILABLE

Okay, at least this is readable to people who have used fork() more than
twice, but you could do so much better!

    include Sysexits
    exit :unavailable

Holy Toledo! It's like we're writing Ruby, but our own made-up dialect in
which variable++ is possible! Well, okay, it's not quite that cool. But it
does look more Rubyish. And no monkeys were patched in the filming of this
episode! All the simpletons still exiting with icky *numbers* can still
continue blithely along, none the wiser.

## Contributing

You can clone the source with Mercurial, submit bug reports, suggestions, 
etc., via the project page:

    https://bitbucket.org/ged/sysexits

Or if you prefer Git, you can clone the source via its Github mirror:

    https://github.com/ged/sysexits

After checking out the source, run:

    $ rake newb

This task will install any missing dependencies, run the tests/specs,
and generate the RDoc.

You can read more super-exited pointless marketing at:

    http://deveiate.org/sysexits.html

Or maybe not.


## License

Copyright (c) 2010, Michael Granger
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice,
  this list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* Neither the name of the author/s, nor the names of the project's
  contributors may be used to endorse or promote products derived from this
  software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
