# Crazy bug of the year

This is the smallest repro-case I could boil it down to.

After cloning and `yarn install`-ing, run `yarn test`.

Notice how it exits with a non-zero exit code with no error at all.
I've only managed to reproduce this behavior with this specific combination of circumstances:

1. A moduleNameMapper-mapped import is used 
2. The import contains double slashes.
3. It's an es6 import.
4. The import is followed by a relative import.
5. It doesn't have to be an es6 import.
