add_libc_testsuite(libc_threads_unittests)

add_libc_unittest(
  call_once_test
  SUITE
    libc_threads_unittests
  SRCS
    call_once_test.cpp
  DEPENDS
    libc.include.threads
    libc.src.threads.call_once
    libc.src.threads.mtx_destroy
    libc.src.threads.mtx_init
    libc.src.threads.mtx_lock
    libc.src.threads.mtx_unlock
    libc.src.threads.thrd_create
    libc.src.threads.thrd_join
)

# Disable thrd_test for now as it is flaky on the bots.
# add_libc_unittest(
#   thrd_test
#   SUITE
#     libc_threads_unittests
#   SRCS
#     thrd_test.cpp
#   DEPENDS
#     libc.include.threads
#     libc.src.errno.__errno_location
#     libc.src.threads.thrd_create
#     libc.src.threads.thrd_join
# )

add_libc_unittest(
  mtx_test
  SUITE
    libc_threads_unittests
  SRCS
    mtx_test.cpp
  DEPENDS
    libc.include.threads
    libc.src.errno.__errno_location
    libc.src.threads.mtx_destroy
    libc.src.threads.mtx_init
    libc.src.threads.mtx_lock
    libc.src.threads.mtx_unlock
    libc.src.threads.thrd_create
    libc.src.threads.thrd_join
)
