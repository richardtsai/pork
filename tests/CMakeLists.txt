add_gtest_target(test_flow_control_queue test_flow_control_queue.cc)
target_link_libraries(test_flow_control_queue Threads::Threads)

add_gtest_target(test_worker test_worker.cc)
target_link_libraries(test_worker
    ${THRIFT_LIB} ${WORKER_LIB} Threads::Threads)

add_gtest_target(test_broker_mq test_broker_mq.cc)
target_link_libraries(test_broker_mq
    ${BROKER_LIB} Threads::Threads)

add_gtest_target(test_broker_handler test_broker_handler.cc)
target_link_libraries(test_broker_handler
    ${BROKER_LIB} Threads::Threads)

add_executable(testing_worker testing_worker.cc)
target_link_libraries(testing_worker ${WORKER_LIB})
