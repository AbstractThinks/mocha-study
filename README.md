##mocha学习使用

###install mocha and mochawesome(report template)
1.npm i -g mocha
2.npm i -g mochawesome

###run mocha
1.mocha a.test.js
2.mocha(Mocha默认运行test子目录里面的测试脚本)
3.mocha --recursive(运行默认test目录及子目录中的测试脚本)
4.mocha --recursive --reporter(-R) mochawesome(生成测试模板) --growl(-G)(将测试结果在桌面显示)
5.mocha --recursive --watch(-w)(监视指定的测试脚本。只要测试脚本有变化，就会自动运行Mocha)

###mocha.opts
  在test目录中使用mocha.opts文件
  在文件中加入mocha参数后run mocha即可
  mocha.opts
    --growl
    --recursive
    --reporter mochawesome
  等同于ocha --recursive -R mochawesome -G
  




