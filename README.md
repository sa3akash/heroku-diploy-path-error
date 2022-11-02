How to deploy apps for free
Deploying single react applications and full-stack web applications using Heroku and Netlify.

Single React App on Heroku
Create a Heroku account.
Create your app.
Download Heroku CLI from here.
Run these codes.
heroku login
git init
heroku git:remote -a <app-name>
heroku create -b https://github.com/mars/create-react-app-buildpack.git
git add .
git commit -am "my first commit"
git push heroku master
Single React App on Netlify
Deploy using the browser
Build your application
yarn build
Drag and drop your build folder to Netlify manual upload section.
Deploy using Github
Connect to the Github
Choose your repository/branch
Change the deployment code to
CI= npm run build
Deploying Full-Stack Apps
Create a Heroku app.
Change your Node app port to
process.env.PORT || <any port number>
Move your front-end app inside the Node app.
Add these codes inside your main JS file in your Node app.
app.use(express.static(path.join(__dirname, "/<front end app folder name>/build")));

app.get('*', (req, res) => {
  res.sendFile(path.join(__dirname, '/<front end app folder name>/build', 'index.html'));
});
Add this script to your package.json in the Node app.
"heroku-postbuild": "cd client && npm install && npm run build"
Change your API URL in your React app.

Set your environment variables on Heroku

Run these codes.

heroku login
git init
heroku git:remote -a <app-name>
git add .
git commit -am "my first commit"
git push heroku master
