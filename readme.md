<h1>Setting up a brand new Ubuntu instance up & ready for mysql</h1>

<p>Download the Ubuntu/Debian APT Repo DEB file from Oracle: https://dev.mysql.com/downloads/repo/apt/</p>
<p>Install the package</p>
<p>sudo apt-get update</p>
<p>sudo apt-get install</p>

<br />
<h2>Run these scripts in Terminal:</h2>
<p>sudo apt-get install mysql-server;</p>
<p>sudo apt install mysql-workbench</p>
<h3>Do NOT install via snap... you run into lots of frustrating problems. If you did, here's the scripts to get started: </h3>
<p>sudo snap install mysql-workbench-community</p>
<p>sudo snap connect mysql-workbench-community:password-manager-service :password-manager-service;</p>
<br />
<h2>Other Notes:</h2>
<p>For writing into the database from the disk you need to enable local_infile in MySQL. Local Infile has to also be enabled on the client side (ex: node-mysql2 uses infileStreamFactory: () => fs.createReadStream(dataPath) option). Script for setting the variable in MySQL: mysql> SET GLOBAL local_infile=1;</p>
<p>Restart server after setting variable</p>
<p>Always start server with the infle flag mysql --local-infile=1</p>
<p>Kudos to here for that sweet info: https://stackoverflow.com/questions/59993844/error-loading-local-data-is-disabled-this-must-be-enabled-on-both-the-client</p>
