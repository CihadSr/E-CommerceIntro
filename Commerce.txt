using Abc.PcSatis.Business.Abstract;
using Abc.PcSatis.DAL.Abstract;
using Abc.PcSatis.Entities.Concrete;
using System;
using System.Collections.Generic;
using System.Text;

namespace Abc.PcSatis.Business.Concrete
{
    public class ProductManager : IProductService
    {
        private IProductDal _productDal;

        public ProductManager(IProductDal productDal)
        {
            _productDal = productDal;
        }
        public void Add(Product product)
        {
            _productDal.Add(product);
        }
//Deleting errors and I don't understand 
        public void Delete(int prodId)
        {
            return _productDal.Delete(prodId);
        }

        public List<Product> GetAll()
        {
            return _productDal.GetList();
        }

        public List<Product> GetByCategory(int categoryId)
        {
            return _productDal.GetList(p => p.CategoryID == categoryId);
        }

        public void Update(Product product)
        {
            _productDal.Update(product);
        }
    }
}
