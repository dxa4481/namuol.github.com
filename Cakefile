fs = require 'fs'
ck = require 'coffeecup'
stylus = require 'stylus'

handle_errors = (err, stdout, stderr) ->
  throw err if err
  console.log stdout + stderr

task 'build', 'Create compiled HTML/CSS output', ->
  console.log 'build her a cake or something...'

  console.log 'building main file'

  result = ck.render fs.readFileSync('src/index.coffee', 'utf-8')
  fs.writeFileSync 'index.html', result

  result = ck.render fs.readFileSync('src/beer.coffee', 'utf-8')
  fs.writeFileSync 'beer.html', result

  result = ck.render fs.readFileSync('src/thanks.coffee', 'utf-8')
  fs.writeFileSync 'thanks.html', result

  console.log 'building css'
  stylus.render fs.readFileSync('src/style.styl','utf-8'), {filename: 'style.css'}, (err, css) ->
    fs.writeFileSync 'style.css', css
