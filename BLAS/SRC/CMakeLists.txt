#######################################################################
#  This is the makefile to create a library for the BLAS.
#  The files are grouped as follows:
#
#       SBLAS1 -- Single precision real BLAS routines
#       CBLAS1 -- Single precision complex BLAS routines
#       DBLAS1 -- Double precision real BLAS routines
#       ZBLAS1 -- Double precision complex BLAS routines
#
#       CB1AUX -- Real BLAS routines called by complex routines
#       ZB1AUX -- D.P. real BLAS routines called by d.p. complex
#                 routines
#
#      ALLBLAS -- Auxiliary routines for Level 2 and 3 BLAS
#
#       SBLAS2 -- Single precision real BLAS2 routines
#       CBLAS2 -- Single precision complex BLAS2 routines
#       DBLAS2 -- Double precision real BLAS2 routines
#       ZBLAS2 -- Double precision complex BLAS2 routines
#
#       SBLAS3 -- Single precision real BLAS3 routines
#       CBLAS3 -- Single precision complex BLAS3 routines
#       DBLAS3 -- Double precision real BLAS3 routines
#       ZBLAS3 -- Double precision complex BLAS3 routines
#
#######################################################################

#---------------------------------------------------------
#  Level 1 BLAS
#---------------------------------------------------------
set(SBLAS1 
  "${dir}/isamax.f" 
  "${dir}/sasum.f" 
  "${dir}/saxpy.f" 
  "${dir}/scopy.f" 
  "${dir}/sdot.f" 
  "${dir}/snrm2.f"
  "${dir}/srot.f" 
  "${dir}/srotg.f" 
  "${dir}/sscal.f" 
  "${dir}/sswap.f" 
  "${dir}/sdsdot.f" 
  "${dir}/srotmg.f" 
  "${dir}/srotm.f"
)

set(CBLAS1 
  "${dir}/scabs1.f" 
  "${dir}/scasum.f" 
  "${dir}/scnrm2.f" 
  "${dir}/icamax.f" 
  "${dir}/caxpy.f" 
  "${dir}/ccopy.f"
  "${dir}/cdotc.f" 
  "${dir}/cdotu.f" 
  "${dir}/csscal.f" 
  "${dir}/crotg.f" 
  "${dir}/cscal.f" 
  "${dir}/cswap.f" 
  "${dir}/csrot.f"
)

set(DBLAS1 
  "${dir}/idamax.f" 
  "${dir}/dasum.f" 
  "${dir}/daxpy.f" 
  "${dir}/dcopy.f" 
  "${dir}/ddot.f" 
  "${dir}/dnrm2.f"
  "${dir}/drot.f" 
  "${dir}/drotg.f" 
  "${dir}/dscal.f" 
  "${dir}/dsdot.f" 
  "${dir}/dswap.f" 
  "${dir}/drotmg.f" 
  "${dir}/drotm.f"
)

set(ZBLAS1 
  "${dir}/dcabs1.f" 
  "${dir}/dzasum.f" 
  "${dir}/dznrm2.f" 
  "${dir}/izamax.f" 
  "${dir}/zaxpy.f" 
  "${dir}/zcopy.f"
  "${dir}/zdotc.f" 
  "${dir}/zdotu.f" 
  "${dir}/zdscal.f" 
  "${dir}/zrotg.f" 
  "${dir}/zscal.f" 
  "${dir}/zswap.f" 
  "${dir}/zdrot.f"
)

set(CB1AUX 
  "${dir}/isamax.f" 
  "${dir}/sasum.f" 
  "${dir}/saxpy.f" 
  "${dir}/scopy.f" 
  "${dir}/snrm2.f" 
  "${dir}/sscal.f"
)

set(ZB1AUX 
  "${dir}/idamax.f" 
  "${dir}/dasum.f" 
  "${dir}/daxpy.f" 
  "${dir}/dcopy.f" 
  "${dir}/dnrm2.f" 
  "${dir}/dscal.f"
)

#---------------------------------------------------------------------
#  Auxiliary routines needed by both the Level 2 and Level 3 BLAS
#---------------------------------------------------------------------
set(ALLBLAS 
  "${dir}/lsame.f" 
  "${dir}/xerbla.f" 
  "${dir}/xerbla_array.f"
)

#---------------------------------------------------------
#  Level 2 BLAS
#---------------------------------------------------------
set(SBLAS2 
  "${dir}/sgemv.f" 
  "${dir}/sgbmv.f" 
  "${dir}/ssymv.f" 
  "${dir}/ssbmv.f" 
  "${dir}/sspmv.f"
  "${dir}/strmv.f" 
  "${dir}/stbmv.f" 
  "${dir}/stpmv.f" 
  "${dir}/strsv.f" 
  "${dir}/stbsv.f" 
  "${dir}/stpsv.f"
  "${dir}/sger.f" 
  "${dir}/ssyr.f" 
  "${dir}/sspr.f" 
  "${dir}/ssyr2.f" 
  "${dir}/sspr2.f"
)

set(CBLAS2 
  "${dir}/cgemv.f" 
  "${dir}/cgbmv.f" 
  "${dir}/chemv.f" 
  "${dir}/chbmv.f" 
  "${dir}/chpmv.f"
  "${dir}/ctrmv.f" 
  "${dir}/ctbmv.f" 
  "${dir}/ctpmv.f" 
  "${dir}/ctrsv.f" 
  "${dir}/ctbsv.f" 
  "${dir}/ctpsv.f"
  "${dir}/cgerc.f" 
  "${dir}/cgeru.f" 
  "${dir}/cher.f" 
  "${dir}/chpr.f" 
  "${dir}/cher2.f"
  "${dir}/chpr2.f"
)

set(DBLAS2 
  "${dir}/dgemv.f" 
  "${dir}/dgbmv.f" 
  "${dir}/dsymv.f" 
  "${dir}/dsbmv.f" 
  "${dir}/dspmv.f"
  "${dir}/dtrmv.f" 
  "${dir}/dtbmv.f" 
  "${dir}/dtpmv.f" 
  "${dir}/dtrsv.f" 
  "${dir}/dtbsv.f" 
  "${dir}/dtpsv.f"
  "${dir}/dger.f" 
  "${dir}/dsyr.f" 
  "${dir}/dspr.f" 
  "${dir}/dsyr2.f" 
  "${dir}/dspr2.f"
)

set(ZBLAS2 
  "${dir}/zgemv.f" 
  "${dir}/zgbmv.f" 
  "${dir}/zhemv.f" 
  "${dir}/zhbmv.f" 
  "${dir}/zhpmv.f"
  "${dir}/ztrmv.f" 
  "${dir}/ztbmv.f" 
  "${dir}/ztpmv.f" 
  "${dir}/ztrsv.f" 
  "${dir}/ztbsv.f" 
  "${dir}/ztpsv.f"
  "${dir}/zgerc.f" 
  "${dir}/zgeru.f" 
  "${dir}/zher.f" 
  "${dir}/zhpr.f" 
  "${dir}/zher2.f" 
  "${dir}/zhpr2.f"
)

#---------------------------------------------------------
#  Level 3 BLAS
#---------------------------------------------------------
set(SBLAS3 
  "${dir}/sgemm.f" 
  "${dir}/ssymm.f" 
  "${dir}/ssyrk.f" 
  "${dir}/ssyr2k.f" 
  "${dir}/strmm.f" 
  "${dir}/strsm.f"
)

set(CBLAS3 
  "${dir}/cgemm.f" 
  "${dir}/csymm.f" 
  "${dir}/csyrk.f" 
  "${dir}/csyr2k.f" 
  "${dir}/ctrmm.f" 
  "${dir}/ctrsm.f"
  "${dir}/chemm.f" 
  "${dir}/cherk.f" 
  "${dir}/cher2k.f"
)

set(DBLAS3 
  "${dir}/dgemm.f" 
  "${dir}/dsymm.f" 
  "${dir}/dsyrk.f" 
  "${dir}/dsyr2k.f" 
  "${dir}/dtrmm.f" 
  "${dir}/dtrsm.f"
)

set(ZBLAS3 
  "${dir}/zgemm.f" 
  "${dir}/zsymm.f" 
  "${dir}/zsyrk.f" 
  "${dir}/zsyr2k.f" 
  "${dir}/ztrmm.f" 
  "${dir}/ztrsm.f"
  "${dir}/zhemm.f" 
  "${dir}/zherk.f" 
  "${dir}/zher2k.f"
)


set(SOURCES)
if("s" IN_LIST arith)
  list(APPEND SOURCES ${SBLAS1} ${ALLBLAS} ${SBLAS2} ${SBLAS3})
endif()
if("d" IN_LIST arith)
  list(APPEND SOURCES ${DBLAS1} ${ALLBLAS} ${DBLAS2} ${DBLAS3})
endif()
if("c" IN_LIST arith)
  list(APPEND SOURCES ${CBLAS1} ${CB1AUX} ${ALLBLAS} ${CBLAS2} ${CBLAS3})
endif()
if("z" IN_LIST arith)
  list(APPEND SOURCES ${ZBLAS1} ${ZB1AUX} ${ALLBLAS} ${ZBLAS2} ${ZBLAS3})
endif()
list(REMOVE_DUPLICATES SOURCES)

set(blas_srcs "${SOURCES}" PARENT_SCOPE)