<h2>Forensic Toolkit Basics</h2>
<a href="forensics">Back</a>
<h3>A Note On FTK Tools</h3>
<p>AccessData.com provides a suite of forensics tools.</p>
<ul>
    <li>Forensic Toolkit (FTK): Referred to as "FTK". This program provides robust forensics analysis options, including disk imaging, file decryption, password cracking, registry file parsing, data carving, reporting, and more. This toolkit has a 5000 file limit on the demo version.</li>
    <li>AccessData FTK Imager: This program is the go-to for creating disk images, features include hash reporting, image mounting, APFS image captures, and more. Especially useful to view and export a smaller subset of folders or files from the evidence tree of an image.</li>
</ul>

<div class="intro">
    <h4>Add Evidence to FTK</h4>
</div>

<div class="steps">
    <h3>FTK</h3>
    <ul>
        <li>Open Forensic Toolkit FTK</li>
        <li>Select “No” to run in Demo Mode</li>
        <li>Start a new case</li>
        <li>Input Case Information (this will be used on the generated report)</li>
        <li>Select Case Path (where you would like the case files stored)</li>
        <li>Forensic Examiner Info (you can leave this blank)</li>
        <li>Case Log Options (information included in case log)</li>
        <li>Processes to Perform</li>
        <ul><li>These options will need to change depending on your objectives. Unselect options you’re not using to shorten processing time.</li></ul>
        <li>Refine Case & Index Defaults</li>
        <ul><li>You can add these options on later as needed, which shortens initial processing time.</ul></li>
        <li>Add Evidence</li>
        <li>Select Next</li>
        <li>Select Finish</li>
    </ul>
    <b>Additional Resources</b>
    <ul><li><a href="https://vimeo.com/384252876" target="_blank">Simplified process of loading forensics image</a></li></ul>
</div>

<div class="intro">
    <h4>FTK Dashboard</h4>
</div>

<div class="steps">
    <h3>Overview Tab</h3>
    <p>Evidence Item: Select the evidence item to see the loaded content.</p>
    <h3>File Status Column</h3>
    <ul>
        <li>Bad Extension: File extension doesn’t match the file type</li>
        <li>Deleted Files and Recycle Bin: files are different because of the additional system files that are created and placed in the recycle bin when a file is marked for deletion</li>
        <li>OLE Subitems: links and embedded items</li>
    </ul>
    <h3>File Category Column</h3>
    <p>Items are broken up by actual file type. word docs, plain text docs, html docs, etc and anything plaintext will be able to be read there. Archives are zipped files. Slack free space (so if it found files in the slack space).</p>
    <h3>Explore Tab</h3>
    <p>Allows us to look at the files like we would through windows explorer. From here we can pick off low-hanging fruit in forensics investigation (my pictures / my documents) folders.</p>
    <h3>Graphics Tab</h3>
    <p>The graphics tab is meant for finding easy stuff and analyzing image files.</p>
    <b>Additional Resources</b>
    <ul>
        <li><a href="https://vimeo.com/384253238" target="_blank">Finding and viewing files with bad extensions</a></li>
        <li><a href="https://vimeo.com/384244998" target="_blank">Bookmarking evidence and creating reports</a></li>
        <li><a href="https://vimeo.com/384252473" target="_blank">Exporting and Viewing Videos</a></li>
    </ul>
</div>

<div class="intro">
    <h4>Performing Basic Text Searches</h4>
</div>
<div class="steps">
    <h3>Build a Word Index</h3>
    <ul>
        <li>Select File > Add Evidence</li>
        <li>Select “Full Text Index” checkbox</li>
            <ul><li>This option takes some time to process. It builds an index with every word that is in the image.</li>
            <li>Allows you to perform text searches using the search field.</li></ul>
    </ul>
    <h3>Build a word index after an image has been processed</h3>
    <p>Tools > Analysis Tools > Full Text Indexing</p>
    <h3>Indexed Search</h3>
    <ul>
        <li>Select the Search Tab</li>
        <li>Select Indexed Search</li>
        <li>Type in term or import from file</li>
        <li>After the search is completed, select “View Item Results” to see results</li>
        <li>Add additional search terms to perform a Compound search</li>
    </ul>
    <b>Additional Resources</b>
    <p><a href="https://vimeo.com/412881969" target="_blank">Expand or narrow searches with stemming (adding ed / ing onto a word)</a></p>
    <p><a href="https://vimeo.com/411790844" target="_blank">Phonics - find words like “raise, race, raze, rays”</a></p>
    <p><a href="https://vimeo.com/411835899" target="_blank">Fuzzy option - spelling errors</a></p>
    <p><a href="https://vimeo.com/411862846" target="_blank">Set date limits</a></p>
    <p><a href="https://vimeo.com/410862313" target="_blank">Size and Filename Patterns</a></p>
    <p><a href="https://vimeo.com/410869512" target="_blank">Using Wildcards in Search String</a></p>
    <p><a href="https://vimeo.com/410871908" target="_blank">Export List of Words</a></p>
    <h3>Regular Expressions</h3>
    <ul>
        <li>Select Search</li>
        <li>Live Search</li>
        <li>Select “Regular Expression” checkbox</li>
        <li>Select > arrow</li>
        <li>A list of prebuilt Regular Expressions appears</li>
    </ul>
    <b>Additional Resources</b>
    <p><a href="https://vimeo.com/542205908" target="_blank">Regular Expressions</a></p>
    <p><a href="https://vimeo.com/407677760" target="_blank">Building Regular Expressions</a></p>
    <p><a href="https://vimeo.com/410290934" target="_blank">Download / Install Regular Expressions</a></p>
</div>