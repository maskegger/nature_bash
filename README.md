# NATURE-BASH

These scripts were written to accompany a [*Nature* Toolbox article](https://www.nature.com/articles/d41586-021-00263-0) (link will go live on 2 Feb 2021) on what researchers can do at the command line. 

To try them out: 

1. If you are on a Mac or Linux, open your Terminal (or similar) application. On Windows, you'll need something like [MobaXterm](https://mobaxterm.mobatek.net/). 
2. From the command prompt, clone this GitHub repository: `git clone https://github.com/jperkel/nature_bash.git`. 
3. Enter the newly created directory: `cd nature_bash`.
4. Make the scripts executable: `chmod +x *.sh`. 
5. Run the scripts in numeric order, being sure to prepend each file name with a period and slash, eg: `./01_init.sh`). This tells the shell where to find these scripts (i.e., the current directory) when that location is not included in your file search `PATH` variable. 
6. You don't have to type the complete filename. Once you type enough of the filename to be uniquely recognized, you can use Bash's 'autocomplete' feature to fill in the rest of the name for you. Try it: type `./01` and then hit the `TAB` key to complete the command.
7. There are six scripts in total:
- [`01_init.sh`](https://github.com/jperkel/nature_bash/blob/main/01_init.sh): Creates a temporary directory (`nature_tmpdir`) beneath the current directory and fills it with dummy files
- [`02_fix_filenames.sh`](https://github.com/jperkel/nature_bash/blob/main/02_fix_filenames.sh): We created 217 files with date-stamped names using the pattern: DD-MM-YYYY, e.g., datafile-01-01-2020.txt, datafile-02-01-2020.txt, etc. This script uses the `sed` command and a for-loop to rename them using the standard YYYYMMDD pattern. 
- [`03_process_data.sh`](https://github.com/jperkel/nature_bash/blob/main/03_process_data.sh): We created a four dummy data files, such as might be output from a spectrophotometer (3 files of "readings" and 1 "background" file). This script pulls those data into a single data file, averages the readings, subtracts the background, and divides by 60 to give a per-second value. The result is a spreadsheet, which is displayed on screen.
- [`04_geo.sh`](https://github.com/jperkel/nature_bash/blob/main/04_geo.sh): This script downloads a compressed gene expression datafile from the NCBI Gene Expression Omnibus database, extracts it, and searches for a gene name given on the command line. Try it with the Cactin gene: `./04_geo.sh Cactin`. 
- [`05_filter_geo.sh`](https://github.com/jperkel/nature_bash/blob/main/05_filter_geo.sh): This script uses `sed` and `awk` to filter the GEO datafile from `04_geo.sh` for records with a p-value < 0.05 and an ensembl_gene_id value other than NA.
- [`99_clean_all.sh`](https://github.com/jperkel/nature_bash/blob/main/99_clean_all.sh): Deletes all temporary files. 

## License. 
(from [https://opensource.org/licenses/BSD-3-Clause](https://opensource.org/licenses/BSD-3-Clause)) Copyright 2021 Jeffrey M. Perkel

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

Neither the name of the copyright holder nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
