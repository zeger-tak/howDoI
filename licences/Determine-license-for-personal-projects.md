# Determining the Best License for Personal Git Repositories

## Requirements
- Free to use by anyone, no payment needed.
- Require a reference to the original repo if any code is used in production.


## Summary of popular licenses
- **MIT License**
  - Permissive license allowing reuse with minimal restrictions.
  - Requires attribution to the original author.
  - Suitable for most personal projects.
  - Check:  https://opensource.org/licenses/MIT
- **Apache License 2.0**
  - Permissive license with explicit grant of patent rights.
  - Requires attribution and a copy of the license.
  - Suitable for projects that may involve patents.
  - Check:  https://www.apache.org/licenses/LICENSE-2.0
- **GNU General Public License (GPL) v3**
  - Strong copyleft license requiring derivative works to also be open source under the same license.
  - Requires attribution and a copy of the license.
  - Suitable for projects where you want to ensure that all modifications remain open source.
  - Check:  https://www.gnu.org/licenses/gpl-3.0.en.html
- **BSD 3-Clause License**
  - Permissive license similar to MIT but with additional clauses.
  - Requires attribution and a disclaimer of warranty.
  - Includes a clause that prevents others from using your name or the names of contributors to endorse or promote derived products without explicit permission.
  - Suitable for projects where you want to allow use in closed source projects, require attribution, and limit endorsement.
  - Check:  https://opensource.org/licenses/BSD-3-Clause
- **Creative Commons Zero (CC0)**
  - Public domain dedication, allowing anyone to use the work for any purpose without restrictions.
  - No attribution required.
  - Suitable for projects where you want to waive all rights and allow maximum freedom of use.

- No suitable license in the options above? Check:  https://choosealicense.com/

## Decision Tree
1. Do you want to allow commercial use of your code?
   - Yes: Go to step 2.
   - No: Consider using a non-commercial license (not covered here).
2. Do you want to require that modifications to your code also be open source?
   - Yes: Consider using GNU GPL v3.
   - No: Go to step 3.
3. Do you want to include a patent grant?
   - Yes: Consider using Apache License 2.0.
   - No: Go to step 4.
4. Do you want to limit the use of your name for endorsement?
   - This means you do not want others to use your name, project name, or the names of contributors to promote or endorse derived products without your explicit permission. For example, if someone uses your code in their project, they cannot claim or imply that you or your contributors endorse their project unless you have given written consent. The BSD 3-Clause License includes this restriction to protect your reputation and prevent unauthorized endorsements.
   - Yes: Consider using BSD 3-Clause License.
   - No: Consider using MIT License.

## Example Scenarios (from most restrictive to least restrictive)
- **Scenario 1**: You want to ensure that any modifications to your code are also shared under the same open-source license (strong copyleft).
  - Recommended License: GNU GPL v3.
- **Scenario 2**: You are concerned about patent rights and want to ensure that users of your code have a clear grant of patent rights, while allowing permissive use and attribution.
  - Recommended License: Apache License 2.0.
- **Scenario 3**: You want to allow use in closed source projects, require attribution in the code base, and prevent your name from being used for endorsement without permission.
  - Recommended License: BSD 3-Clause License.
- **Scenario 4**: You want to prevent others from using your name or the names of contributors to endorse derived products without permission, but do not require attribution in closed source projects.
  - Recommended License: BSD 3-Clause License.
- **Scenario 5**: You want to allow anyone to use your code for any purpose, including commercial use, and you don't mind if they modify it without sharing those modifications or attributing you in closed source projects.
  - Recommended License: MIT License.
- **Scenario 6**: You want to waive all your rights and allow anyone to use your code for any purpose without any restrictions or attribution.
  - Recommended License: Creative Commons Zero (CC0).

I.e (from most restrictive to least restrictive):
1. Code repository for a software tool that you want to ensure remains open source: GNU GPL v3.
2. Code repository for a project that may involve patents: Apache License 2.0.
3. Code repository for a project where you want to allow closed source use, require attribution, and limit endorsement: BSD 3-Clause License.
4. Code repository for a project where you want to limit endorsement: BSD 3-Clause License.
5. Code repository for a library that others can use in their projects without restrictions: MIT License.
6. Code repository for a project where you want to waive all rights: Creative Commons Zero (CC0).
