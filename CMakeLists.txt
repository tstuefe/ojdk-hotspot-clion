cmake_minimum_required(VERSION 3.8)
project(jdkjdk)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++98 -D__STDC_FORMAT_MACROS -D__STDC_LIMIT_MACROS -D__STDC_CONSTANT_MACROS -D_GNU_SOURCE -D_REENTRANT -DSUPPORTS_CLOCK_MONOTONIC -DLINUX -DVM_LITTLE_ENDIAN -D_LP64=1 -DASSERT -DCHECK_UNHANDLED_OOPS -DTARGET_ARCH_x86 -DINCLUDE_SUFFIX_OS=_linux -DINCLUDE_SUFFIX_CPU=_x86 -DINCLUDE_SUFFIX_COMPILER=_gcc -DTARGET_COMPILER_gcc -DAMD64 -DHOTSPOT_LIB_ARCH='amd64' -DCOMPILER1 -DCOMPILER2 -DINCLUDE_ZGC=0 -DTHIS_FILE=''")

set (CMAKE_CXX_STANDARD 98)

include_directories(
	../output-fastdebug/hotspot/variant-server/libjvm/objs/precompiled
	../output-fastdebug/hotspot/variant-server/gensrc/adfiles
	src/hotspot/share
	src/hotspot/os/linux
	src/hotspot/os/posix
	src/hotspot/cpu/x86
	src/hotspot/os_cpu/linux_x86
	../output-fastdebug/hotspot/variant-server/gensrc
	src/hotspot/share/precompiled
	src/hotspot/share/include
	src/hotspot/os/posix/include
	../output-fastdebug/support/modules_include/java.base
	../output-fastdebug/support/modules_include/java.base/linux
	src/java.base/share/native/libjimage
)


set(SOURCE_FILES
src/hotspot/cpu/x86/abstractInterpreter_x86.cpp
src/hotspot/cpu/x86/assembler_x86.cpp
src/hotspot/cpu/x86/c1_CodeStubs_x86.cpp
src/hotspot/cpu/x86/c1_FpuStackSim_x86.cpp
src/hotspot/cpu/x86/c1_FrameMap_x86.cpp
src/hotspot/cpu/x86/c1_LinearScan_x86.cpp
src/hotspot/cpu/x86/c1_LIRAssembler_x86.cpp
src/hotspot/cpu/x86/c1_LIRGenerator_x86.cpp
src/hotspot/cpu/x86/c1_LIR_x86.cpp
src/hotspot/cpu/x86/c1_MacroAssembler_x86.cpp
src/hotspot/cpu/x86/c1_Runtime1_x86.cpp
src/hotspot/cpu/x86/c2_init_x86.cpp
src/hotspot/cpu/x86/compiledIC_aot_x86_64.cpp
src/hotspot/cpu/x86/compiledIC_x86.cpp
src/hotspot/cpu/x86/depChecker_x86.cpp
src/hotspot/cpu/x86/frame_x86.cpp
src/hotspot/cpu/x86/gc/g1/g1BarrierSetAssembler_x86.cpp
src/hotspot/cpu/x86/gc/shared/barrierSetAssembler_x86.cpp
src/hotspot/cpu/x86/gc/shared/cardTableBarrierSetAssembler_x86.cpp
src/hotspot/cpu/x86/gc/shared/modRefBarrierSetAssembler_x86.cpp
src/hotspot/cpu/x86/icache_x86.cpp
src/hotspot/cpu/x86/icBuffer_x86.cpp
src/hotspot/cpu/x86/interp_masm_x86.cpp
src/hotspot/cpu/x86/interpreterRT_x86_64.cpp
src/hotspot/cpu/x86/jniFastGetField_x86_64.cpp
src/hotspot/cpu/x86/jvmciCodeInstaller_x86.cpp
src/hotspot/cpu/x86/macroAssembler_x86_cos.cpp
src/hotspot/cpu/x86/macroAssembler_x86.cpp
src/hotspot/cpu/x86/macroAssembler_x86_exp.cpp
src/hotspot/cpu/x86/macroAssembler_x86_log10.cpp
src/hotspot/cpu/x86/macroAssembler_x86_log.cpp
src/hotspot/cpu/x86/macroAssembler_x86_pow.cpp
src/hotspot/cpu/x86/macroAssembler_x86_sha.cpp
src/hotspot/cpu/x86/macroAssembler_x86_sin.cpp
src/hotspot/cpu/x86/macroAssembler_x86_tan.cpp
src/hotspot/cpu/x86/methodHandles_x86.cpp
src/hotspot/cpu/x86/nativeInst_x86.cpp
src/hotspot/cpu/x86/rdtsc_x86.cpp
src/hotspot/cpu/x86/register_definitions_x86.cpp
src/hotspot/cpu/x86/registerMap_x86.cpp
src/hotspot/cpu/x86/register_x86.cpp
src/hotspot/cpu/x86/relocInfo_x86.cpp
src/hotspot/cpu/x86/runtime_x86_64.cpp
src/hotspot/cpu/x86/sharedRuntime_x86_64.cpp
src/hotspot/cpu/x86/sharedRuntime_x86.cpp
src/hotspot/cpu/x86/stubGenerator_x86_64.cpp
src/hotspot/cpu/x86/stubRoutines_x86_64.cpp
src/hotspot/cpu/x86/stubRoutines_x86.cpp
src/hotspot/cpu/x86/templateInterpreterGenerator_x86_64.cpp
src/hotspot/cpu/x86/templateInterpreterGenerator_x86.cpp
src/hotspot/cpu/x86/templateTable_x86.cpp
src/hotspot/cpu/x86/vmreg_x86.cpp
src/hotspot/cpu/x86/vm_version_ext_x86.cpp
src/hotspot/cpu/x86/vm_version_x86.cpp
src/hotspot/cpu/x86/vtableStubs_x86_64.cpp
src/hotspot/os_cpu/linux_x86/assembler_linux_x86.cpp
src/hotspot/os_cpu/linux_x86/os_linux_x86.cpp
src/hotspot/os_cpu/linux_x86/thread_linux_x86.cpp
src/hotspot/os_cpu/linux_x86/vm_version_linux_x86.cpp
src/hotspot/os/linux/attachListener_linux.cpp
src/hotspot/os/linux/decoder_linux.cpp
src/hotspot/os/linux/osContainer_linux.cpp
src/hotspot/os/linux/os_linux.cpp
src/hotspot/os/linux/os_perf_linux.cpp
src/hotspot/os/linux/osThread_linux.cpp
src/hotspot/os/linux/perfMemory_linux.cpp
src/hotspot/os/linux/threadCritical_linux.cpp
src/hotspot/os/posix/jvm_posix.cpp
src/hotspot/os/posix/os_posix.cpp
src/hotspot/os/posix/semaphore_posix.cpp
src/hotspot/os/posix/threadLocalStorage_posix.cpp
src/hotspot/os/posix/vmError_posix.cpp
src/hotspot/share/adlc/adlparse.cpp
src/hotspot/share/adlc/archDesc.cpp
src/hotspot/share/adlc/arena.cpp
src/hotspot/share/adlc/dfa.cpp
src/hotspot/share/adlc/dict2.cpp
src/hotspot/share/adlc/filebuff.cpp
src/hotspot/share/adlc/forms.cpp
src/hotspot/share/adlc/formsopt.cpp
src/hotspot/share/adlc/formssel.cpp
src/hotspot/share/adlc/main.cpp
src/hotspot/share/adlc/output_c.cpp
src/hotspot/share/adlc/output_h.cpp
src/hotspot/share/aot/aotCodeHeap.cpp
src/hotspot/share/aot/aotCompiledMethod.cpp
src/hotspot/share/aot/aotLoader.cpp
src/hotspot/share/aot/compiledIC_aot.cpp
src/hotspot/share/asm/assembler.cpp
src/hotspot/share/asm/codeBuffer.cpp
src/hotspot/share/asm/register.cpp
src/hotspot/share/c1/c1_Canonicalizer.cpp
src/hotspot/share/c1/c1_CFGPrinter.cpp
src/hotspot/share/c1/c1_Compilation.cpp
src/hotspot/share/c1/c1_Compiler.cpp
src/hotspot/share/c1/c1_Defs.cpp
src/hotspot/share/c1/c1_FrameMap.cpp
src/hotspot/share/c1/c1_globals.cpp
src/hotspot/share/c1/c1_GraphBuilder.cpp
src/hotspot/share/c1/c1_Instruction.cpp
src/hotspot/share/c1/c1_InstructionPrinter.cpp
src/hotspot/share/c1/c1_IR.cpp
src/hotspot/share/c1/c1_LinearScan.cpp
src/hotspot/share/c1/c1_LIRAssembler.cpp
src/hotspot/share/c1/c1_LIR.cpp
src/hotspot/share/c1/c1_LIRGenerator.cpp
src/hotspot/share/c1/c1_Optimizer.cpp
src/hotspot/share/c1/c1_RangeCheckElimination.cpp
src/hotspot/share/c1/c1_Runtime1.cpp
src/hotspot/share/c1/c1_ValueMap.cpp
src/hotspot/share/c1/c1_ValueSet.cpp
src/hotspot/share/c1/c1_ValueStack.cpp
src/hotspot/share/c1/c1_ValueType.cpp
src/hotspot/share/ci/bcEscapeAnalyzer.cpp
src/hotspot/share/ci/ciArray.cpp
src/hotspot/share/ci/ciArrayKlass.cpp
src/hotspot/share/ci/ciBaseObject.cpp
src/hotspot/share/ci/ciCallSite.cpp
src/hotspot/share/ci/ciConstant.cpp
src/hotspot/share/ci/ciConstantPoolCache.cpp
src/hotspot/share/ci/ciEnv.cpp
src/hotspot/share/ci/ciExceptionHandler.cpp
src/hotspot/share/ci/ciField.cpp
src/hotspot/share/ci/ciFlags.cpp
src/hotspot/share/ci/ciInstance.cpp
src/hotspot/share/ci/ciInstanceKlass.cpp
src/hotspot/share/ci/ciKlass.cpp
src/hotspot/share/ci/ciMemberName.cpp
src/hotspot/share/ci/ciMetadata.cpp
src/hotspot/share/ci/ciMethodBlocks.cpp
src/hotspot/share/ci/ciMethod.cpp
src/hotspot/share/ci/ciMethodData.cpp
src/hotspot/share/ci/ciMethodHandle.cpp
src/hotspot/share/ci/ciMethodType.cpp
src/hotspot/share/ci/ciNullObject.cpp
src/hotspot/share/ci/ciObjArray.cpp
src/hotspot/share/ci/ciObjArrayKlass.cpp
src/hotspot/share/ci/ciObject.cpp
src/hotspot/share/ci/ciObjectFactory.cpp
src/hotspot/share/ci/ciReplay.cpp
src/hotspot/share/ci/ciSignature.cpp
src/hotspot/share/ci/ciStreams.cpp
src/hotspot/share/ci/ciSymbol.cpp
src/hotspot/share/ci/ciTypeArray.cpp
src/hotspot/share/ci/ciTypeArrayKlass.cpp
src/hotspot/share/ci/ciType.cpp
src/hotspot/share/ci/ciTypeFlow.cpp
src/hotspot/share/ci/ciUtilities.cpp
src/hotspot/share/classfile/altHashing.cpp
src/hotspot/share/classfile/bytecodeAssembler.cpp
src/hotspot/share/classfile/classFileError.cpp
src/hotspot/share/classfile/classFileParser.cpp
src/hotspot/share/classfile/classFileStream.cpp
src/hotspot/share/classfile/classListParser.cpp
src/hotspot/share/classfile/classLoader.cpp
src/hotspot/share/classfile/classLoaderData.cpp
src/hotspot/share/classfile/classLoaderExt.cpp
src/hotspot/share/classfile/classLoaderHierarchyDCmd.cpp
src/hotspot/share/classfile/classLoaderStats.cpp
src/hotspot/share/classfile/compactHashtable.cpp
src/hotspot/share/classfile/defaultMethods.cpp
src/hotspot/share/classfile/dictionary.cpp
src/hotspot/share/classfile/javaAssertions.cpp
src/hotspot/share/classfile/javaClasses.cpp
src/hotspot/share/classfile/klassFactory.cpp
src/hotspot/share/classfile/loaderConstraints.cpp
src/hotspot/share/classfile/metadataOnStackMark.cpp
src/hotspot/share/classfile/moduleEntry.cpp
src/hotspot/share/classfile/modules.cpp
src/hotspot/share/classfile/packageEntry.cpp
src/hotspot/share/classfile/placeholders.cpp
src/hotspot/share/classfile/protectionDomainCache.cpp
src/hotspot/share/classfile/resolutionErrors.cpp
src/hotspot/share/classfile/sharedPathsMiscInfo.cpp
src/hotspot/share/classfile/stackMapFrame.cpp
src/hotspot/share/classfile/stackMapTable.cpp
src/hotspot/share/classfile/stringTable.cpp
src/hotspot/share/classfile/symbolTable.cpp
src/hotspot/share/classfile/systemDictionary.cpp
src/hotspot/share/classfile/systemDictionaryShared.cpp
src/hotspot/share/classfile/verificationType.cpp
src/hotspot/share/classfile/verifier.cpp
src/hotspot/share/classfile/vmSymbols.cpp
src/hotspot/share/code/codeBlob.cpp
src/hotspot/share/code/codeCache.cpp
src/hotspot/share/code/codeHeapState.cpp
src/hotspot/share/code/compiledIC.cpp
src/hotspot/share/code/compiledMethod.cpp
src/hotspot/share/code/compressedStream.cpp
src/hotspot/share/code/debugInfo.cpp
src/hotspot/share/code/debugInfoRec.cpp
src/hotspot/share/code/dependencies.cpp
src/hotspot/share/code/dependencyContext.cpp
src/hotspot/share/code/exceptionHandlerTable.cpp
src/hotspot/share/code/icBuffer.cpp
src/hotspot/share/code/location.cpp
src/hotspot/share/code/nmethod.cpp
src/hotspot/share/code/oopRecorder.cpp
src/hotspot/share/code/pcDesc.cpp
src/hotspot/share/code/relocInfo.cpp
src/hotspot/share/code/relocInfo_ext.cpp
src/hotspot/share/code/scopeDesc.cpp
src/hotspot/share/code/stubs.cpp
src/hotspot/share/code/vmreg.cpp
src/hotspot/share/code/vtableStubs.cpp
src/hotspot/share/compiler/abstractCompiler.cpp
src/hotspot/share/compiler/compileBroker.cpp
src/hotspot/share/compiler/compileLog.cpp
src/hotspot/share/compiler/compilerDefinitions.cpp
src/hotspot/share/compiler/compilerDirectives.cpp
src/hotspot/share/compiler/compilerOracle.cpp
src/hotspot/share/compiler/compileTask.cpp
src/hotspot/share/compiler/directivesParser.cpp
src/hotspot/share/compiler/disassembler.cpp
src/hotspot/share/compiler/methodLiveness.cpp
src/hotspot/share/compiler/methodMatcher.cpp
src/hotspot/share/compiler/oopMap.cpp
src/hotspot/share/gc/cms/adaptiveFreeList.cpp
src/hotspot/share/gc/cms/allocationStats.cpp
src/hotspot/share/gc/cms/cmsArguments.cpp
src/hotspot/share/gc/cms/cmsCardTable.cpp
src/hotspot/share/gc/cms/cmsCollectorPolicy.cpp
src/hotspot/share/gc/cms/cmsGCStats.cpp
src/hotspot/share/gc/cms/cmsHeap.cpp
src/hotspot/share/gc/cms/cmsLockVerifier.cpp
src/hotspot/share/gc/cms/compactibleFreeListSpace.cpp
src/hotspot/share/gc/cms/concurrentMarkSweepGeneration.cpp
src/hotspot/share/gc/cms/concurrentMarkSweepThread.cpp
src/hotspot/share/gc/cms/freeChunk.cpp
src/hotspot/share/gc/cms/gSpaceCounters.cpp
src/hotspot/share/gc/cms/jvmFlagConstraintsCMS.cpp
src/hotspot/share/gc/cms/parNewGeneration.cpp
src/hotspot/share/gc/cms/promotionInfo.cpp
src/hotspot/share/gc/cms/vmCMSOperations.cpp
src/hotspot/share/gc/cms/yieldingWorkgroup.cpp
src/hotspot/share/gc/epsilon/epsilonArguments.cpp
src/hotspot/share/gc/epsilon/epsilonBarrierSet.cpp
src/hotspot/share/gc/epsilon/epsilonHeap.cpp
src/hotspot/share/gc/epsilon/epsilonMemoryPool.cpp
src/hotspot/share/gc/epsilon/epsilonMonitoringSupport.cpp
src/hotspot/share/gc/g1/c1/g1BarrierSetC1.cpp
src/hotspot/share/gc/g1/c2/g1BarrierSetC2.cpp
src/hotspot/share/gc/g1/collectionSetChooser.cpp
src/hotspot/share/gc/g1/dirtyCardQueue.cpp
src/hotspot/share/gc/g1/g1Allocator.cpp
src/hotspot/share/gc/g1/g1AllocRegion.cpp
src/hotspot/share/gc/g1/g1Analytics.cpp
src/hotspot/share/gc/g1/g1Arguments.cpp
src/hotspot/share/gc/g1/g1BarrierSet.cpp
src/hotspot/share/gc/g1/g1BarrierSetRuntime.cpp
src/hotspot/share/gc/g1/g1BiasedArray.cpp
src/hotspot/share/gc/g1/g1BlockOffsetTable.cpp
src/hotspot/share/gc/g1/g1CardCounts.cpp
src/hotspot/share/gc/g1/g1CardTable.cpp
src/hotspot/share/gc/g1/g1CodeBlobClosure.cpp
src/hotspot/share/gc/g1/g1CodeCacheRemSet.cpp
src/hotspot/share/gc/g1/g1CollectedHeap.cpp
src/hotspot/share/gc/g1/g1CollectionSet.cpp
src/hotspot/share/gc/g1/g1CollectorPolicy.cpp
src/hotspot/share/gc/g1/g1ConcurrentMarkBitMap.cpp
src/hotspot/share/gc/g1/g1ConcurrentMark.cpp
src/hotspot/share/gc/g1/g1ConcurrentMarkObjArrayProcessor.cpp
src/hotspot/share/gc/g1/g1ConcurrentMarkThread.cpp
src/hotspot/share/gc/g1/g1ConcurrentRefine.cpp
src/hotspot/share/gc/g1/g1ConcurrentRefineThread.cpp
src/hotspot/share/gc/g1/g1EvacFailure.cpp
src/hotspot/share/gc/g1/g1EvacStats.cpp
src/hotspot/share/gc/g1/g1FromCardCache.cpp
src/hotspot/share/gc/g1/g1FullCollector.cpp
src/hotspot/share/gc/g1/g1FullGCAdjustTask.cpp
src/hotspot/share/gc/g1/g1FullGCCompactionPoint.cpp
src/hotspot/share/gc/g1/g1FullGCCompactTask.cpp
src/hotspot/share/gc/g1/g1FullGCMarker.cpp
src/hotspot/share/gc/g1/g1FullGCMarkTask.cpp
src/hotspot/share/gc/g1/g1FullGCOopClosures.cpp
src/hotspot/share/gc/g1/g1FullGCPrepareTask.cpp
src/hotspot/share/gc/g1/g1FullGCReferenceProcessorExecutor.cpp
src/hotspot/share/gc/g1/g1FullGCScope.cpp
src/hotspot/share/gc/g1/g1FullGCTask.cpp
src/hotspot/share/gc/g1/g1GCPhaseTimes.cpp
src/hotspot/share/gc/g1/g1HeapRegionEventSender.cpp
src/hotspot/share/gc/g1/g1HeapSizingPolicy.cpp
src/hotspot/share/gc/g1/g1HeapSizingPolicy_ext.cpp
src/hotspot/share/gc/g1/g1HeapTransition.cpp
src/hotspot/share/gc/g1/g1HeapVerifier.cpp
src/hotspot/share/gc/g1/g1HotCardCache.cpp
src/hotspot/share/gc/g1/g1IHOPControl.cpp
src/hotspot/share/gc/g1/g1MemoryPool.cpp
src/hotspot/share/gc/g1/g1MMUTracker.cpp
src/hotspot/share/gc/g1/g1MonitoringSupport.cpp
src/hotspot/share/gc/g1/g1OopClosures.cpp
src/hotspot/share/gc/g1/g1PageBasedVirtualSpace.cpp
src/hotspot/share/gc/g1/g1ParScanThreadState.cpp
src/hotspot/share/gc/g1/g1Policy.cpp
src/hotspot/share/gc/g1/g1RegionMarkStatsCache.cpp
src/hotspot/share/gc/g1/g1RegionToSpaceMapper.cpp
src/hotspot/share/gc/g1/g1RemSet.cpp
src/hotspot/share/gc/g1/g1RemSetSummary.cpp
src/hotspot/share/gc/g1/g1RemSetTrackingPolicy.cpp
src/hotspot/share/gc/g1/g1RootClosures.cpp
src/hotspot/share/gc/g1/g1RootProcessor.cpp
src/hotspot/share/gc/g1/g1StringDedup.cpp
src/hotspot/share/gc/g1/g1StringDedupQueue.cpp
src/hotspot/share/gc/g1/g1StringDedupStat.cpp
src/hotspot/share/gc/g1/g1SurvivorRegions.cpp
src/hotspot/share/gc/g1/g1YoungGenSizer.cpp
src/hotspot/share/gc/g1/g1YoungRemSetSamplingThread.cpp
src/hotspot/share/gc/g1/heapRegion.cpp
src/hotspot/share/gc/g1/heapRegionManager.cpp
src/hotspot/share/gc/g1/heapRegionRemSet.cpp
src/hotspot/share/gc/g1/heapRegionSet.cpp
src/hotspot/share/gc/g1/heapRegionTracer.cpp
src/hotspot/share/gc/g1/heapRegionType.cpp
src/hotspot/share/gc/g1/jvmFlagConstraintsG1.cpp
src/hotspot/share/gc/g1/ptrQueue.cpp
src/hotspot/share/gc/g1/satbMarkQueue.cpp
src/hotspot/share/gc/g1/sparsePRT.cpp
src/hotspot/share/gc/g1/survRateGroup.cpp
src/hotspot/share/gc/g1/vm_operations_g1.cpp
src/hotspot/share/gc/parallel/adjoiningGenerations.cpp
src/hotspot/share/gc/parallel/adjoiningVirtualSpaces.cpp
src/hotspot/share/gc/parallel/asPSOldGen.cpp
src/hotspot/share/gc/parallel/asPSYoungGen.cpp
src/hotspot/share/gc/parallel/gcAdaptivePolicyCounters.cpp
src/hotspot/share/gc/parallel/gcTaskManager.cpp
src/hotspot/share/gc/parallel/gcTaskThread.cpp
src/hotspot/share/gc/parallel/generationSizer.cpp
src/hotspot/share/gc/parallel/immutableSpace.cpp
src/hotspot/share/gc/parallel/jvmFlagConstraintsParallel.cpp
src/hotspot/share/gc/parallel/mutableNUMASpace.cpp
src/hotspot/share/gc/parallel/mutableSpace.cpp
src/hotspot/share/gc/parallel/objectStartArray.cpp
src/hotspot/share/gc/parallel/parallelArguments.cpp
src/hotspot/share/gc/parallel/parallelScavengeHeap.cpp
src/hotspot/share/gc/parallel/parMarkBitMap.cpp
src/hotspot/share/gc/parallel/pcTasks.cpp
src/hotspot/share/gc/parallel/psAdaptiveSizePolicy.cpp
src/hotspot/share/gc/parallel/psCardTable.cpp
src/hotspot/share/gc/parallel/psCompactionManager.cpp
src/hotspot/share/gc/parallel/psGCAdaptivePolicyCounters.cpp
src/hotspot/share/gc/parallel/psGenerationCounters.cpp
src/hotspot/share/gc/parallel/psMarkSweep.cpp
src/hotspot/share/gc/parallel/psMarkSweepDecorator.cpp
src/hotspot/share/gc/parallel/psMemoryPool.cpp
src/hotspot/share/gc/parallel/psOldGen.cpp
src/hotspot/share/gc/parallel/psParallelCompact.cpp
src/hotspot/share/gc/parallel/psPromotionLAB.cpp
src/hotspot/share/gc/parallel/psPromotionManager.cpp
src/hotspot/share/gc/parallel/psScavenge.cpp
src/hotspot/share/gc/parallel/psTasks.cpp
src/hotspot/share/gc/parallel/psVirtualspace.cpp
src/hotspot/share/gc/parallel/psYoungGen.cpp
src/hotspot/share/gc/parallel/spaceCounters.cpp
src/hotspot/share/gc/parallel/vmPSOperations.cpp
src/hotspot/share/gc/serial/cSpaceCounters.cpp
src/hotspot/share/gc/serial/defNewGeneration.cpp
src/hotspot/share/gc/serial/genMarkSweep.cpp
src/hotspot/share/gc/serial/markSweep.cpp
src/hotspot/share/gc/serial/serialArguments.cpp
src/hotspot/share/gc/serial/serialHeap.cpp
src/hotspot/share/gc/serial/tenuredGeneration.cpp
src/hotspot/share/gc/shared/accessBarrierSupport.cpp
src/hotspot/share/gc/shared/adaptiveSizePolicy.cpp
src/hotspot/share/gc/shared/ageTable.cpp
src/hotspot/share/gc/shared/ageTableTracer.cpp
src/hotspot/share/gc/shared/allocTracer.cpp
src/hotspot/share/gc/shared/barrierSet.cpp
src/hotspot/share/gc/shared/blockOffsetTable.cpp
src/hotspot/share/gc/shared/c1/barrierSetC1.cpp
src/hotspot/share/gc/shared/c1/cardTableBarrierSetC1.cpp
src/hotspot/share/gc/shared/c1/modRefBarrierSetC1.cpp
src/hotspot/share/gc/shared/c2/barrierSetC2.cpp
src/hotspot/share/gc/shared/c2/cardTableBarrierSetC2.cpp
src/hotspot/share/gc/shared/c2/modRefBarrierSetC2.cpp
src/hotspot/share/gc/shared/cardGeneration.cpp
src/hotspot/share/gc/shared/cardTableBarrierSet.cpp
src/hotspot/share/gc/shared/cardTable.cpp
src/hotspot/share/gc/shared/cardTableRS.cpp
src/hotspot/share/gc/shared/collectedHeap.cpp
src/hotspot/share/gc/shared/collectorCounters.cpp
src/hotspot/share/gc/shared/collectorPolicy.cpp
src/hotspot/share/gc/shared/concurrentGCPhaseManager.cpp
src/hotspot/share/gc/shared/concurrentGCThread.cpp
src/hotspot/share/gc/shared/gcArguments.cpp
src/hotspot/share/gc/shared/gcCause.cpp
src/hotspot/share/gc/shared/gcConfig.cpp
src/hotspot/share/gc/shared/gcConfiguration.cpp
src/hotspot/share/gc/shared/gcId.cpp
src/hotspot/share/gc/shared/gcLocker.cpp
src/hotspot/share/gc/shared/gcPolicyCounters.cpp
src/hotspot/share/gc/shared/gcStats.cpp
src/hotspot/share/gc/shared/gcTimer.cpp
src/hotspot/share/gc/shared/gcTrace.cpp
src/hotspot/share/gc/shared/gcTraceSend.cpp
src/hotspot/share/gc/shared/gcTraceTime.cpp
src/hotspot/share/gc/shared/gcUtil.cpp
src/hotspot/share/gc/shared/genCollectedHeap.cpp
src/hotspot/share/gc/shared/generationCounters.cpp
src/hotspot/share/gc/shared/generation.cpp
src/hotspot/share/gc/shared/generationSpec.cpp
src/hotspot/share/gc/shared/genMemoryPools.cpp
src/hotspot/share/gc/shared/hSpaceCounters.cpp
src/hotspot/share/gc/shared/jvmFlagConstraintsGC.cpp
src/hotspot/share/gc/shared/memAllocator.cpp
src/hotspot/share/gc/shared/objectCountEventSender.cpp
src/hotspot/share/gc/shared/oopStorage.cpp
src/hotspot/share/gc/shared/plab.cpp
src/hotspot/share/gc/shared/preservedMarks.cpp
src/hotspot/share/gc/shared/referencePolicy.cpp
src/hotspot/share/gc/shared/referenceProcessor.cpp
src/hotspot/share/gc/shared/referenceProcessorPhaseTimes.cpp
src/hotspot/share/gc/shared/softRefGenPolicy.cpp
src/hotspot/share/gc/shared/softRefPolicy.cpp
src/hotspot/share/gc/shared/space.cpp
src/hotspot/share/gc/shared/spaceDecorator.cpp
src/hotspot/share/gc/shared/stringdedup/stringDedup.cpp
src/hotspot/share/gc/shared/stringdedup/stringDedupQueue.cpp
src/hotspot/share/gc/shared/stringdedup/stringDedupStat.cpp
src/hotspot/share/gc/shared/stringdedup/stringDedupTable.cpp
src/hotspot/share/gc/shared/stringdedup/stringDedupThread.cpp
src/hotspot/share/gc/shared/strongRootsScope.cpp
src/hotspot/share/gc/shared/suspendibleThreadSet.cpp
src/hotspot/share/gc/shared/taskqueue.cpp
src/hotspot/share/gc/shared/threadLocalAllocBuffer.cpp
src/hotspot/share/gc/shared/vmGCOperations.cpp
src/hotspot/share/gc/shared/weakProcessor.cpp
src/hotspot/share/gc/shared/workerDataArray.cpp
src/hotspot/share/gc/shared/workgroup.cpp
src/hotspot/share/interpreter/abstractInterpreter.cpp
src/hotspot/share/interpreter/bytecode.cpp
src/hotspot/share/interpreter/bytecodeHistogram.cpp
src/hotspot/share/interpreter/bytecodeInterpreter.cpp
src/hotspot/share/interpreter/bytecodes.cpp
src/hotspot/share/interpreter/bytecodeStream.cpp
src/hotspot/share/interpreter/bytecodeTracer.cpp
src/hotspot/share/interpreter/cppInterpreter.cpp
src/hotspot/share/interpreter/cppInterpreterGenerator.cpp
src/hotspot/share/interpreter/interpreter.cpp
src/hotspot/share/interpreter/interpreterRuntime.cpp
src/hotspot/share/interpreter/invocationCounter.cpp
src/hotspot/share/interpreter/linkResolver.cpp
src/hotspot/share/interpreter/oopMapCache.cpp
src/hotspot/share/interpreter/rewriter.cpp
src/hotspot/share/interpreter/templateInterpreter.cpp
src/hotspot/share/interpreter/templateInterpreterGenerator.cpp
src/hotspot/share/interpreter/templateTable.cpp
src/hotspot/share/jfr/dcmd/jfrDcmds.cpp
src/hotspot/share/jfr/instrumentation/jfrEventClassTransformer.cpp
src/hotspot/share/jfr/instrumentation/jfrJvmtiAgent.cpp
src/hotspot/share/jfr/jfr.cpp
src/hotspot/share/jfr/jni/jfrGetAllEventClasses.cpp
src/hotspot/share/jfr/jni/jfrJavaCall.cpp
src/hotspot/share/jfr/jni/jfrJavaSupport.cpp
src/hotspot/share/jfr/jni/jfrJniMethod.cpp
src/hotspot/share/jfr/jni/jfrJniMethodRegistration.cpp
src/hotspot/share/jfr/jni/jfrUpcalls.cpp
src/hotspot/share/jfr/leakprofiler/chains/bfsClosure.cpp
src/hotspot/share/jfr/leakprofiler/chains/bitset.cpp
src/hotspot/share/jfr/leakprofiler/chains/dfsClosure.cpp
src/hotspot/share/jfr/leakprofiler/chains/edge.cpp
src/hotspot/share/jfr/leakprofiler/chains/edgeQueue.cpp
src/hotspot/share/jfr/leakprofiler/chains/edgeStore.cpp
src/hotspot/share/jfr/leakprofiler/chains/edgeUtils.cpp
src/hotspot/share/jfr/leakprofiler/chains/rootSetClosure.cpp
src/hotspot/share/jfr/leakprofiler/checkpoint/objectSampleCheckpoint.cpp
src/hotspot/share/jfr/leakprofiler/checkpoint/objectSampleDescription.cpp
src/hotspot/share/jfr/leakprofiler/checkpoint/objectSampleWriter.cpp
src/hotspot/share/jfr/leakprofiler/checkpoint/rootResolver.cpp
src/hotspot/share/jfr/leakprofiler/emitEventOperation.cpp
src/hotspot/share/jfr/leakprofiler/leakProfiler.cpp
src/hotspot/share/jfr/leakprofiler/sampling/objectSampler.cpp
src/hotspot/share/jfr/leakprofiler/sampling/sampleList.cpp
src/hotspot/share/jfr/leakprofiler/sampling/samplePriorityQueue.cpp
src/hotspot/share/jfr/leakprofiler/utilities/granularTimer.cpp
src/hotspot/share/jfr/leakprofiler/utilities/saveRestore.cpp
src/hotspot/share/jfr/periodic/jfrModuleEvent.cpp
src/hotspot/share/jfr/periodic/jfrNetworkUtilization.cpp
src/hotspot/share/jfr/periodic/jfrOSInterface.cpp
src/hotspot/share/jfr/periodic/jfrPeriodic.cpp
src/hotspot/share/jfr/periodic/jfrThreadCPULoadEvent.cpp
src/hotspot/share/jfr/periodic/jfrThreadDumpEvent.cpp
src/hotspot/share/jfr/periodic/sampling/jfrCallTrace.cpp
src/hotspot/share/jfr/periodic/sampling/jfrThreadSampler.cpp
src/hotspot/share/jfr/recorder/checkpoint/jfrCheckpointBlob.cpp
src/hotspot/share/jfr/recorder/checkpoint/jfrCheckpointManager.cpp
src/hotspot/share/jfr/recorder/checkpoint/jfrCheckpointWriter.cpp
src/hotspot/share/jfr/recorder/checkpoint/jfrMetadataEvent.cpp
src/hotspot/share/jfr/recorder/checkpoint/types/jfrThreadGroup.cpp
src/hotspot/share/jfr/recorder/checkpoint/types/jfrThreadState.cpp
src/hotspot/share/jfr/recorder/checkpoint/types/jfrType.cpp
src/hotspot/share/jfr/recorder/checkpoint/types/jfrTypeManager.cpp
src/hotspot/share/jfr/recorder/checkpoint/types/jfrTypeSet.cpp
src/hotspot/share/jfr/recorder/checkpoint/types/jfrTypeSetUtils.cpp
src/hotspot/share/jfr/recorder/checkpoint/types/traceid/jfrTraceId.cpp
src/hotspot/share/jfr/recorder/checkpoint/types/traceid/jfrTraceIdEpoch.cpp
src/hotspot/share/jfr/recorder/jfrEventSetting.cpp
src/hotspot/share/jfr/recorder/jfrRecorder.cpp
src/hotspot/share/jfr/recorder/repository/jfrChunkSizeNotifier.cpp
src/hotspot/share/jfr/recorder/repository/jfrChunkState.cpp
src/hotspot/share/jfr/recorder/repository/jfrChunkWriter.cpp
src/hotspot/share/jfr/recorder/repository/jfrEmergencyDump.cpp
src/hotspot/share/jfr/recorder/repository/jfrRepository.cpp
src/hotspot/share/jfr/recorder/service/jfrEvent.cpp
src/hotspot/share/jfr/recorder/service/jfrMemorySizer.cpp
src/hotspot/share/jfr/recorder/service/jfrOptionSet.cpp
src/hotspot/share/jfr/recorder/service/jfrPostBox.cpp
src/hotspot/share/jfr/recorder/service/jfrRecorderService.cpp
src/hotspot/share/jfr/recorder/service/jfrRecorderThread.cpp
src/hotspot/share/jfr/recorder/service/jfrRecorderThreadLoop.cpp
src/hotspot/share/jfr/recorder/stacktrace/jfrStackTraceRepository.cpp
src/hotspot/share/jfr/recorder/storage/jfrBuffer.cpp
src/hotspot/share/jfr/recorder/storage/jfrStorageControl.cpp
src/hotspot/share/jfr/recorder/storage/jfrStorage.cpp
src/hotspot/share/jfr/recorder/storage/jfrVirtualMemory.cpp
src/hotspot/share/jfr/recorder/stringpool/jfrStringPoolBuffer.cpp
src/hotspot/share/jfr/recorder/stringpool/jfrStringPool.cpp
src/hotspot/share/jfr/recorder/stringpool/jfrStringPoolWriter.cpp
src/hotspot/share/jfr/support/jfrAllocationTracer.cpp
src/hotspot/share/jfr/support/jfrEventClass.cpp
src/hotspot/share/jfr/support/jfrFlush.cpp
src/hotspot/share/jfr/support/jfrStackTraceMark.cpp
src/hotspot/share/jfr/support/jfrThreadLocal.cpp
src/hotspot/share/jfr/utilities/jfrAllocation.cpp
src/hotspot/share/jfr/utilities/jfrJavaLog.cpp
src/hotspot/share/jfr/utilities/jfrTimeConverter.cpp
src/hotspot/share/jfr/utilities/jfrTime.cpp
src/hotspot/share/jfr/writers/jfrJavaEventWriter.cpp
src/hotspot/share/jvmci/compilerRuntime.cpp
src/hotspot/share/jvmci/jvmciCodeInstaller.cpp
src/hotspot/share/jvmci/jvmciCompiler.cpp
src/hotspot/share/jvmci/jvmciCompilerToVM.cpp
src/hotspot/share/jvmci/jvmciCompilerToVMInit.cpp
src/hotspot/share/jvmci/jvmciEnv.cpp
src/hotspot/share/jvmci/jvmci_globals.cpp
src/hotspot/share/jvmci/jvmciJavaClasses.cpp
src/hotspot/share/jvmci/jvmciRuntime.cpp
src/hotspot/share/jvmci/vmStructs_jvmci.cpp
src/hotspot/share/libadt/dict.cpp
src/hotspot/share/libadt/set.cpp
src/hotspot/share/libadt/vectset.cpp
src/hotspot/share/logging/logConfiguration.cpp
src/hotspot/share/logging/logDecorations.cpp
src/hotspot/share/logging/logDecorators.cpp
src/hotspot/share/logging/logDiagnosticCommand.cpp
src/hotspot/share/logging/logFileOutput.cpp
src/hotspot/share/logging/logFileStreamOutput.cpp
src/hotspot/share/logging/logLevel.cpp
src/hotspot/share/logging/logMessageBuffer.cpp
src/hotspot/share/logging/logOutput.cpp
src/hotspot/share/logging/logOutputList.cpp
src/hotspot/share/logging/logSelection.cpp
src/hotspot/share/logging/logSelectionList.cpp
src/hotspot/share/logging/logStream.cpp
src/hotspot/share/logging/logTag.cpp
src/hotspot/share/logging/logTagSet.cpp
src/hotspot/share/logging/logTagSetDescriptions.cpp
src/hotspot/share/memory/allocation.cpp
src/hotspot/share/memory/arena.cpp
src/hotspot/share/memory/filemap.cpp
src/hotspot/share/memory/guardedMemory.cpp
src/hotspot/share/memory/heap.cpp
src/hotspot/share/memory/heapInspection.cpp
src/hotspot/share/memory/heapShared.cpp
src/hotspot/share/memory/iterator.cpp
src/hotspot/share/memory/memRegion.cpp
src/hotspot/share/memory/metaspace/blockFreelist.cpp
src/hotspot/share/memory/metaspace/chunkManager.cpp
src/hotspot/share/memory/metaspaceClosure.cpp
src/hotspot/share/memory/metaspaceCounters.cpp
src/hotspot/share/memory/metaspace.cpp
src/hotspot/share/memory/metaspace/metachunk.cpp
src/hotspot/share/memory/metaspace/metaDebug.cpp
src/hotspot/share/memory/metaspace/metaspaceCommon.cpp
src/hotspot/share/memory/metaspace/metaspaceDCmd.cpp
src/hotspot/share/memory/metaspace/metaspaceStatistics.cpp
src/hotspot/share/memory/metaspace/occupancyMap.cpp
src/hotspot/share/memory/metaspace/printCLDMetaspaceInfoClosure.cpp
src/hotspot/share/memory/metaspace/printMetaspaceInfoKlassClosure.cpp
src/hotspot/share/memory/metaspaceShared.cpp
src/hotspot/share/memory/metaspace/smallBlocks.cpp
src/hotspot/share/memory/metaspace/spaceManager.cpp
src/hotspot/share/memory/metaspaceTracer.cpp
src/hotspot/share/memory/metaspace/virtualSpaceList.cpp
src/hotspot/share/memory/metaspace/virtualSpaceNode.cpp
src/hotspot/share/memory/oopFactory.cpp
src/hotspot/share/memory/operator_new.cpp
src/hotspot/share/memory/resourceArea.cpp
src/hotspot/share/memory/universe.cpp
src/hotspot/share/memory/virtualspace.cpp
src/hotspot/share/oops/accessBackend.cpp
src/hotspot/share/oops/access.cpp
src/hotspot/share/oops/annotations.cpp
src/hotspot/share/oops/arrayKlass.cpp
src/hotspot/share/oops/compiledICHolder.cpp
src/hotspot/share/oops/constantPool.cpp
src/hotspot/share/oops/constMethod.cpp
src/hotspot/share/oops/cpCache.cpp
src/hotspot/share/oops/generateOopMap.cpp
src/hotspot/share/oops/instanceKlass.cpp
src/hotspot/share/oops/instanceMirrorKlass.cpp
src/hotspot/share/oops/instanceOop.cpp
src/hotspot/share/oops/instanceRefKlass.cpp
src/hotspot/share/oops/klass.cpp
src/hotspot/share/oops/klassVtable.cpp
src/hotspot/share/oops/markOop.cpp
src/hotspot/share/oops/metadata.cpp
src/hotspot/share/oops/methodCounters.cpp
src/hotspot/share/oops/method.cpp
src/hotspot/share/oops/methodData.cpp
src/hotspot/share/oops/objArrayKlass.cpp
src/hotspot/share/oops/objArrayOop.cpp
src/hotspot/share/oops/oop.cpp
src/hotspot/share/oops/oopsHierarchy.cpp
src/hotspot/share/oops/reflectionAccessorImplKlassHelper.cpp
src/hotspot/share/oops/symbol.cpp
src/hotspot/share/oops/typeArrayKlass.cpp
src/hotspot/share/oops/weakHandle.cpp
src/hotspot/share/opto/addnode.cpp
src/hotspot/share/opto/arraycopynode.cpp
src/hotspot/share/opto/block.cpp
src/hotspot/share/opto/buildOopMap.cpp
src/hotspot/share/opto/bytecodeInfo.cpp
src/hotspot/share/opto/c2compiler.cpp
src/hotspot/share/opto/c2_globals.cpp
src/hotspot/share/opto/callGenerator.cpp
src/hotspot/share/opto/callnode.cpp
src/hotspot/share/opto/castnode.cpp
src/hotspot/share/opto/cfgnode.cpp
src/hotspot/share/opto/chaitin.cpp
src/hotspot/share/opto/classes.cpp
src/hotspot/share/opto/coalesce.cpp
src/hotspot/share/opto/compile.cpp
src/hotspot/share/opto/connode.cpp
src/hotspot/share/opto/convertnode.cpp
src/hotspot/share/opto/countbitsnode.cpp
src/hotspot/share/opto/divnode.cpp
src/hotspot/share/opto/doCall.cpp
src/hotspot/share/opto/domgraph.cpp
src/hotspot/share/opto/escape.cpp
src/hotspot/share/opto/gcm.cpp
src/hotspot/share/opto/generateOptoStub.cpp
src/hotspot/share/opto/graphKit.cpp
src/hotspot/share/opto/idealGraphPrinter.cpp
src/hotspot/share/opto/idealKit.cpp
src/hotspot/share/opto/ifg.cpp
src/hotspot/share/opto/ifnode.cpp
src/hotspot/share/opto/indexSet.cpp
src/hotspot/share/opto/intrinsicnode.cpp
src/hotspot/share/opto/lcm.cpp
src/hotspot/share/opto/library_call.cpp
src/hotspot/share/opto/live.cpp
src/hotspot/share/opto/locknode.cpp
src/hotspot/share/opto/loopnode.cpp
src/hotspot/share/opto/loopopts.cpp
src/hotspot/share/opto/loopPredicate.cpp
src/hotspot/share/opto/loopTransform.cpp
src/hotspot/share/opto/loopUnswitch.cpp
src/hotspot/share/opto/machnode.cpp
src/hotspot/share/opto/macroArrayCopy.cpp
src/hotspot/share/opto/macro.cpp
src/hotspot/share/opto/matcher.cpp
src/hotspot/share/opto/mathexactnode.cpp
src/hotspot/share/opto/memnode.cpp
src/hotspot/share/opto/movenode.cpp
src/hotspot/share/opto/mulnode.cpp
src/hotspot/share/opto/multnode.cpp
src/hotspot/share/opto/narrowptrnode.cpp
src/hotspot/share/opto/node.cpp
src/hotspot/share/opto/opaquenode.cpp
src/hotspot/share/opto/opcodes.cpp
src/hotspot/share/opto/output.cpp
src/hotspot/share/opto/parse1.cpp
src/hotspot/share/opto/parse2.cpp
src/hotspot/share/opto/parse3.cpp
src/hotspot/share/opto/parseHelper.cpp
src/hotspot/share/opto/phase.cpp
src/hotspot/share/opto/phaseX.cpp
src/hotspot/share/opto/postaloc.cpp
src/hotspot/share/opto/regalloc.cpp
src/hotspot/share/opto/regmask.cpp
src/hotspot/share/opto/reg_split.cpp
src/hotspot/share/opto/replacednodes.cpp
src/hotspot/share/opto/rootnode.cpp
src/hotspot/share/opto/runtime.cpp
src/hotspot/share/opto/split_if.cpp
src/hotspot/share/opto/stringopts.cpp
src/hotspot/share/opto/subnode.cpp
src/hotspot/share/opto/superword.cpp
src/hotspot/share/opto/type.cpp
src/hotspot/share/opto/vectornode.cpp
src/hotspot/share/prims/cdsoffsets.cpp
src/hotspot/share/prims/evmCompat.cpp
src/hotspot/share/prims/forte.cpp
src/hotspot/share/prims/jniCheck.cpp
src/hotspot/share/prims/jni.cpp
src/hotspot/share/prims/jniFastGetField.cpp
src/hotspot/share/prims/jvm.cpp
src/hotspot/share/prims/jvmtiClassFileReconstituter.cpp
src/hotspot/share/prims/jvmtiCodeBlobEvents.cpp
src/hotspot/share/prims/jvmtiEnvBase.cpp
src/hotspot/share/prims/jvmtiEnv.cpp
src/hotspot/share/prims/jvmtiEnvThreadState.cpp
src/hotspot/share/prims/jvmtiEventController.cpp
src/hotspot/share/prims/jvmtiExport.cpp
src/hotspot/share/prims/jvmtiExtensions.cpp
src/hotspot/share/prims/jvmtiGetLoadedClasses.cpp
src/hotspot/share/prims/jvmtiImpl.cpp
src/hotspot/share/prims/jvmtiManageCapabilities.cpp
src/hotspot/share/prims/jvmtiRawMonitor.cpp
src/hotspot/share/prims/jvmtiRedefineClasses.cpp
src/hotspot/share/prims/jvmtiTagMap.cpp
src/hotspot/share/prims/jvmtiThreadState.cpp
src/hotspot/share/prims/jvmtiTrace.cpp
src/hotspot/share/prims/jvmtiUtil.cpp
src/hotspot/share/prims/methodComparator.cpp
src/hotspot/share/prims/methodHandles.cpp
src/hotspot/share/prims/nativeLookup.cpp
src/hotspot/share/prims/perf.cpp
src/hotspot/share/prims/privilegedStack.cpp
src/hotspot/share/prims/resolvedMethodTable.cpp
src/hotspot/share/prims/stackwalk.cpp
src/hotspot/share/prims/unsafe.cpp
src/hotspot/share/prims/wbtestmethods/parserTests.cpp
src/hotspot/share/prims/whitebox.cpp
src/hotspot/share/runtime/arguments.cpp
src/hotspot/share/runtime/arguments_ext.cpp
src/hotspot/share/runtime/basicLock.cpp
src/hotspot/share/runtime/biasedLocking.cpp
src/hotspot/share/runtime/compilationPolicy.cpp
src/hotspot/share/runtime/deoptimization.cpp
src/hotspot/share/runtime/fieldDescriptor.cpp
src/hotspot/share/runtime/fieldType.cpp
src/hotspot/share/runtime/flags/jvmFlagConstraintList.cpp
src/hotspot/share/runtime/flags/jvmFlagConstraintsCompiler.cpp
src/hotspot/share/runtime/flags/jvmFlagConstraintsRuntime.cpp
src/hotspot/share/runtime/flags/jvmFlag.cpp
src/hotspot/share/runtime/flags/jvmFlagRangeList.cpp
src/hotspot/share/runtime/flags/jvmFlagWriteableList.cpp
src/hotspot/share/runtime/frame.cpp
src/hotspot/share/runtime/globals.cpp
src/hotspot/share/runtime/handles.cpp
src/hotspot/share/runtime/handshake.cpp
src/hotspot/share/runtime/icache.cpp
src/hotspot/share/runtime/init.cpp
src/hotspot/share/runtime/interfaceSupport.cpp
src/hotspot/share/runtime/javaCalls.cpp
src/hotspot/share/runtime/java.cpp
src/hotspot/share/runtime/jniHandles.cpp
src/hotspot/share/runtime/jniPeriodicChecker.cpp
src/hotspot/share/runtime/memprofiler.cpp
src/hotspot/share/runtime/monitorChunk.cpp
src/hotspot/share/runtime/mutex.cpp
src/hotspot/share/runtime/mutexLocker.cpp
src/hotspot/share/runtime/objectMonitor.cpp
src/hotspot/share/runtime/orderAccess.cpp
src/hotspot/share/runtime/os.cpp
src/hotspot/share/runtime/osThread.cpp
src/hotspot/share/runtime/park.cpp
src/hotspot/share/runtime/perfData.cpp
src/hotspot/share/runtime/perfMemory.cpp
src/hotspot/share/runtime/reflection.cpp
src/hotspot/share/runtime/reflectionUtils.cpp
src/hotspot/share/runtime/relocator.cpp
src/hotspot/share/runtime/rframe.cpp
src/hotspot/share/runtime/rtmLocking.cpp
src/hotspot/share/runtime/safepoint.cpp
src/hotspot/share/runtime/safepointMechanism.cpp
src/hotspot/share/runtime/safepointVerifiers.cpp
src/hotspot/share/runtime/serviceThread.cpp
src/hotspot/share/runtime/sharedRuntime.cpp
src/hotspot/share/runtime/sharedRuntimeTrans.cpp
src/hotspot/share/runtime/sharedRuntimeTrig.cpp
src/hotspot/share/runtime/signature.cpp
src/hotspot/share/runtime/simpleThresholdPolicy.cpp
src/hotspot/share/runtime/stackValueCollection.cpp
src/hotspot/share/runtime/stackValue.cpp
src/hotspot/share/runtime/statSampler.cpp
src/hotspot/share/runtime/stubCodeGenerator.cpp
src/hotspot/share/runtime/stubRoutines.cpp
src/hotspot/share/runtime/sweeper.cpp
src/hotspot/share/runtime/synchronizer.cpp
src/hotspot/share/runtime/task.cpp
src/hotspot/share/runtime/thread.cpp
src/hotspot/share/runtime/threadHeapSampler.cpp
src/hotspot/share/runtime/threadSMR.cpp
src/hotspot/share/runtime/timer.cpp
src/hotspot/share/runtime/timerTrace.cpp
src/hotspot/share/runtime/unhandledOops.cpp
src/hotspot/share/runtime/vframeArray.cpp
src/hotspot/share/runtime/vframe.cpp
src/hotspot/share/runtime/vframe_hp.cpp
src/hotspot/share/runtime/vm_operations.cpp
src/hotspot/share/runtime/vmStructs.cpp
src/hotspot/share/runtime/vmThread.cpp
src/hotspot/share/runtime/vm_version.cpp
src/hotspot/share/services/attachListener.cpp
src/hotspot/share/services/classLoadingService.cpp
src/hotspot/share/services/diagnosticArgument.cpp
src/hotspot/share/services/diagnosticCommand.cpp
src/hotspot/share/services/diagnosticFramework.cpp
src/hotspot/share/services/dtraceAttacher.cpp
src/hotspot/share/services/gcNotifier.cpp
src/hotspot/share/services/heapDumper.cpp
src/hotspot/share/services/lowMemoryDetector.cpp
src/hotspot/share/services/mallocSiteTable.cpp
src/hotspot/share/services/mallocTracker.cpp
src/hotspot/share/services/management.cpp
src/hotspot/share/services/memBaseline.cpp
src/hotspot/share/services/memoryManager.cpp
src/hotspot/share/services/memoryPool.cpp
src/hotspot/share/services/memoryService.cpp
src/hotspot/share/services/memReporter.cpp
src/hotspot/share/services/memTracker.cpp
src/hotspot/share/services/nmtCommon.cpp
src/hotspot/share/services/nmtDCmd.cpp
src/hotspot/share/services/runtimeService.cpp
src/hotspot/share/services/threadService.cpp
src/hotspot/share/services/virtualMemoryTracker.cpp
src/hotspot/share/services/writeableFlags.cpp
src/hotspot/share/utilities/accessFlags.cpp
src/hotspot/share/utilities/bitMap.cpp
src/hotspot/share/utilities/constantTag.cpp
src/hotspot/share/utilities/copy.cpp
src/hotspot/share/utilities/debug.cpp
src/hotspot/share/utilities/decoder.cpp
src/hotspot/share/utilities/decoder_elf.cpp
src/hotspot/share/utilities/elfFile.cpp
src/hotspot/share/utilities/elfFuncDescTable.cpp
src/hotspot/share/utilities/elfStringTable.cpp
src/hotspot/share/utilities/elfSymbolTable.cpp
src/hotspot/share/utilities/errorReporter.cpp
src/hotspot/share/utilities/events.cpp
src/hotspot/share/utilities/exceptions.cpp
src/hotspot/share/utilities/formatBuffer.cpp
src/hotspot/share/utilities/globalCounter.cpp
src/hotspot/share/utilities/globalDefinitions.cpp
src/hotspot/share/utilities/growableArray.cpp
src/hotspot/share/utilities/hashtable.cpp
src/hotspot/share/utilities/histogram.cpp
src/hotspot/share/utilities/internalVMTests.cpp
src/hotspot/share/utilities/intHisto.cpp
src/hotspot/share/utilities/json.cpp
src/hotspot/share/utilities/nativeCallStack.cpp
src/hotspot/share/utilities/numberSeq.cpp
src/hotspot/share/utilities/ostream.cpp
src/hotspot/share/utilities/preserveException.cpp
src/hotspot/share/utilities/sizes.cpp
src/hotspot/share/utilities/spinYield.cpp
src/hotspot/share/utilities/stringUtils.cpp
src/hotspot/share/utilities/ticks.cpp
src/hotspot/share/utilities/utf8.cpp
src/hotspot/share/utilities/vmError.cpp
src/hotspot/share/utilities/xmlstream.cpp
        )


add_executable(jdkjdk ${SOURCE_FILES})

