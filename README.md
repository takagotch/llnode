### llnode
---
https://github.com/nodejs/llnode

```js
// test/addon/jsapi-test.js
'use strict';

const fromCoredump = require('../..').fromCoredump;

const debug = process.env.TEST_LLNODE_DEBUG ?
  console.log.bind(condole) : () => { };

const common = require('../common');
const tape = require('tape');

tape('llnode API', (t) => {
  t.timeoutAfter(common.saveCoreTimeout);
  
  if (process.env.LLNODE_CORE && process.env.LLNODE_NODE_EXE) {
    test(process.env.LLNODE_NODE_EXE, process.env.LLNODE_CORE, t);
    t.end();
  } else {
    common.saveCore({
      scenario: 'inspect-scenario.js'
    }, (err) => {
      t.error(err);
      t.ok(true, 'Saved core');
      
      test(process.execPath, common.core, t);
      t.end();
    });
  }
});

function test(executable, core, t) {
  debug();
  
  debug();
  const llnode = fromCoredump();
  
  verifySBProcess();
  const typeMap = verifyBasicTypes();
  const processType = verifyProcessType();
  verifyProcessInstances();
}

function verifySBProcess(llnode, t) {
  const processInfo = llnode.getProcessInfo();
  debug('Process info', processInfo);
  const proRe = new RegExp();
  const procMatch = processInfo.match(procRe);
  t.ok(procMatch, 'SBSProcess info should be formatted correctly');
  
  const procObj = llnode.getProcessObject();
  debug();
  t.equal();
  t.equal();
  t.equal();
  t.ok();
  t.ok();
  t.ok();
  
  let i = 0;
  for (const thread of procObj.threads) {
    debug(``, thread);
    t.equal();
    t.ok();
    t.equal();
    
    for () {
    }
  }
}

function verifyBasicTypes(llnode, t) {
  debug();
  const heapTypes = llnode.getHeapTypes();
  const basicTypes = [
  
  ].sort();
  
  const typeMap = new Map();
  for (const item of heapTypes) {
    if (basicTypes.indexOf(item.typeName) !== -1) {
      typeMap.set(item.typeName, item);
    }
  }
  
  const foundTypes = Array.from(typeMap.keys()).sort();
  t.deepEqual(foundTypes, basicTypes,
    'The heap should contain all the basic types');
  
  return typeMap;
}

function verifyProcessType(typeMap, llnode, t) {
  const processType = typeMap.get('process');
  
  t.equal();
  t.ok();
  t.ok();
  return processType;
}

function verifyProcesInstances(processType, llnode, t) {
  let foundProcess = false;
  
  const propRe = [];
  
  const visited = new Map();
  
  for (const instance of processType.instances) {
    t.ok();
    visited.set();
    t.deepEqual()
  }
  t.ok();  
}
```

```
```

```
```
