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
  
  6.mocha --recursive -R markdown > result.md(result.html)(生成测试文档)
  
###异步测试
  Mocha默认每个测试用例最多执行2000毫秒, -t参数可修改执行时间
  
  mocha -t 5000 a.test.js
  
###mocha.opts
  在test目录中使用mocha.opts文件
  
  在文件中加入mocha参数后run mocha即可
  
  mocha.opts
    
    --growl
    
    --recursive
    
    --reporter mochawesome
    
  等同于ocha --recursive -R mochawesome -G


###DEMO
  var expect = require('chai').expect;(引入断言库)

  describe('单元测试名', function() {
    it('测试用例信息', function() {
      expect(fn(arguments)).to.be.equal(result);
    });
  });
  
  // 相等或不相等
  
  expect(1 + 1).to.be.equal(2);
  
  expect(1 + 1).to.be.not.equal(10);
  
  expect(obj).to.be.deep.equal({ a: 'a' });
  
  // 布尔值为true
  expect('a').to.be.ok;
  expect(false).to.not.be.ok;
  
  // typeof
  
  expect('a').to.be.a('string');
  
  expect({ a: 'a' }).to.be.an('object');
  
  expect(foo).to.be.an.instanceof(Foo);
  
  // include
  expect([1,2,3]).to.include(2);
  
  expect('foobar').to.contain('foo');
  
  expect({ foo: 'bar', hello: 'universe' }).to.include.keys('foo');
  
  // empty
  
  expect([]).to.be.empty;
  
  expect('').to.be.empty;
  
  expect({}).to.be.empty;
  
  // match
  expect('foobar').to.match(/^foo/);
  

    describe('hooks', function() {

      before(function() {
        // 在测试用例it之前运行
      });

      after(function() {
        // 在测试用例it之后运行
      });

      beforeEach(function() {
        // 在每个测试用例it之前运行
      });

      afterEach(function() {
        // 在每个测试用例it之后运行
      });
      
    });

  
参考： 阮一峰的网络日志  测试框架 Mocha 实例教程(http://www.ruanyifeng.com/blog/2015/12/a-mocha-tutorial-of-examples.html)
  
  
  




