require.paths.push __dirname + "/lib"
process.env['PATH'] = __dirname + "/bin:" + process.env['PATH']

{print} = require 'sys'
{spawn} = require 'child_process'

task 'build', 'Build CoffeeScript source files', ->
  coffee = spawn 'coffee', ['-cw', '-o', 'lib', 'src']
  coffee.stdout.on 'data', (data) -> print data.toString()

task 'test', 'Run test suite', ->
  {testrunner} = require 'nodeunit'
  process.chdir __dirname
  testrunner.run ['test']
